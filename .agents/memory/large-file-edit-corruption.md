---
name: Large markdown file corruption via Edit tool
description: An Edit tool call on a large, multi-section .md file produced mid-sentence content splicing (unrelated earlier section text interleaved into the new text) even though the old_string match was exact and unique. Cause unconfirmed (possibly a stale/concurrent write race), but the failure mode is silent — the tool reports success and the diff looks fine in isolation.
---

## What happened
While rewriting one section (~80 lines) of a ~3800-line course chapter file using the `Edit` tool, the resulting file had the new section's text cut off mid-sentence, followed immediately by a full duplicate of the file's title + table of contents + two earlier sections, before finally resuming into the (correct, untouched) MCQ block that came after the edited section. The `Edit` call itself did not error and matched its `old_string` uniquely.

This is the same class of bug seen previously with sequential `ShellExec` heredoc appends to the same large file (see prior incident): content interleaving, not clean duplication — so a simple `sort file | uniq -d` line-dedup check does NOT reliably catch it, since most interleaved lines are individually unique.

## Why
Root cause unconfirmed. Suspect: some prior write (possibly from an earlier session/turn) left the file in a state where a section was already duplicated/corrupted in a way that wasn't caught by earlier verification, and the next `Edit` call's replacement landed adjacent to that latent corruption, making it look freshly introduced.

## How to apply
- After any Edit/Write to a large (1000+ line), multi-section generated document, always run a structural grep check before trusting the result: count and list all section headers (e.g. `grep -n "^## Topic"`), all repeating banner/footer markers, and confirm counts match expectations (no duplicates, no missing sections).
- Do not rely solely on `sort file | uniq -d` to catch corruption in prose files — it only catches exact duplicate lines, not spliced/interleaved paragraphs.
- If corruption is found, don't try to patch around it with more Edit calls on the same corrupted region. Instead: extract the known-clean spans with `sed -n 'X,Yp'` into temp files, write the corrected middle section fresh via `WriteFile` to a temp file, `cat` the parts back together, and only then overwrite the real file. Re-run the structural grep check after reassembly.
