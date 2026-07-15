# Chapter 7 — Tool Aur Programming Language — Hacking Ki ABC
### By TWH (Afsar Ali) | Technical White Hat

---

## 📚 Table of Contents

| # | Topic | Jump |
|---|---|---|
| 7.1 | Tool Kya Hota Hai — Hacking Ki Duniya Ka Sabse Common Word | [➜ Jao](#-topic-71--tool-kya-hota-hai--hacking-ki-duniya-ka-sabse-common-word) |
| 7.2 | Programming Language Kya Hoti Hai Aur Kitne Type Ki Hoti Hain | [➜ Jao](#-topic-72--programming-language-kya-hoti-hai-aur-kitne-type-ki-hoti-hain) |

---
---

okay guys — pehle ke 6 chapters mein tumne bahut kuch seekh liya hai. computer kaise kaam karta hai, networking kaise chalti hai, Linux ka command-line, Kali Linux, aur Termux — sab cover ho gaya.

**badhai ho**, kyunki yeh saari neev (foundation) taiyar karna sabse boring lekin sabse zaroori kaam tha, aur tumne woh kar liya.

ab yahan se aage — jo bhi chapters aayenge — unme tum **actual hacking tools** use karna seekhoge (Nmap, Metasploit, Wireshark, aur bhi bahut kuch). lekin usse pehle, ek chhota lekin **bahut zaroori** chapter — jisme sirf 2 cheezein clear karni hain:

1. **"Tool" kehte kise hain** — yeh word ab se tumhari life mein baar-baar aayega.
2. **"Programming Language" kya hoti hai aur kitne type ki hoti hain** — kyunki har tool kisi na kisi language mein hi bana hota hai.

is chapter mein na koi installation hai, na koi command practice — sirf **samajhna** hai. chalo, welcome karte hain **Chapter 7** mein.

---
---

## 📌 Topic 7.1 — Tool Kya Hota Hai — Hacking Ki Duniya Ka Sabse Common Word

---

### ek seedhi baat

okay guys, ab aap logon ne bahut kuch seekh liya hai, aur ab se aap apni hacking ki life mein ek common word **bahut** sunne aur use karne wale ho — aur woh hai **"Tool"**.

har hacking video, har course, har article mein tumhe yeh line milegi — *"is tool ka use karke yeh kaam kar sakte ho"*. toh sabse pehle clear kar lete hain — **yeh "tool" hota kya hai.**

---

### tool = app / software, bas itni si baat

zyada lamba nahi khinchte is topic ko — seedhi baat:

> **Tool basically ek app ya software hi hota hai** — jaisa tumhare phone mein WhatsApp ek app hai, ya jaisa Termux khud ek app hai, ya jaisa Kali Linux ek poora software (OS) hai — waise hi hacking ka "tool" bhi ek program hota hai jo **ek specific kaam** karne ke liye banaya gaya hota hai.

example se dekho:

- **Nmap** naam ka tool hai — uska kaam hai network mein devices aur ports dhundna.
- **Wireshark** naam ka tool hai — uska kaam hai network ka traffic dekhna.
- **Metasploit** naam ka tool hai — uska kaam hai vulnerabilities test karna.

teeno "tools" hain, lekin teeno alag-alag kaam karte hain — jaise tumhare phone mein Camera app photo khinchti hai aur Calculator app hisaab karta hai, dono apps hain, kaam alag hai.

---

### toh Termux aur Kali Linux se tool ka kya connection hai

seedha connection hai:

> **Termux aur Kali Linux tools "chalane" ki jagah hain — khud tool nahi hain.**

Termux ek app hai jo tumhare phone mein Linux jaisa terminal deta hai, aur Kali Linux ek poora OS hai jo PC pe chalta hai — **dono ke andar hi hum yeh tools install karke chalayenge.** matlab Nmap, Metasploit, Wireshark jaise tools — yeh sab Termux ke andar bhi chal sakte hain aur Kali Linux ke andar bhi.

toh jo bhi tumne pichle chapters mein seekha (Termux, Kali) — woh us "ghar" ki tarah hai jahan ab hum "tools" laa kar rakhenge aur use karenge.

---

### ek line mein

> **Tool ek app/software hi hai, jo ek specific kaam karne ke liye banaya gaya hota hai. Termux aur Kali Linux woh jagah hain jahan hum yeh tools install karke chalate hain.**

---

## 🧠 MCQ Set — Topic 7.1

---

**Q1.** hacking ki duniya mein "tool" ka seedha matlab kya hai?

- A) sirf hardware ka koi part
- B) ek app/software jo ek specific kaam karne ke liye banaya gaya ho
- C) ek website jahan hacking sikhaya jaata hai
- D) sirf Kali Linux ka doosra naam

✅ **Sahi Jawab: B**
> Tool basically ek program hota hai jo ek particular kaam ke liye banaya gaya hota hai — jaise app ya software.

---

**Q2.** Nmap aur Wireshark dono "tools" hain, lekin dono alag hain kyunki —

- A) ek Android ke liye hai, doosra sirf Windows ke liye
- B) dono ka kaam alag hai — Nmap network scan karta hai, Wireshark traffic dekhta hai
- C) ek free hai, doosra paid hai
- D) dono asal mein same tool hain, sirf naam alag hai

✅ **Sahi Jawab: B**
> har tool ek specific kaam ke liye banta hai — Nmap scanning ke liye, Wireshark packet analysis ke liye.

---

**Q3.** Termux aur Kali Linux ka tools se kya rishta hai?

- A) Termux aur Kali khud tools hain
- B) Termux aur Kali woh jagah hain jahan tools install karke chalaye jaate hain
- C) Termux mein tools kabhi nahi chal sakte
- D) Kali Linux sirf browsing ke liye hai, tools ke liye nahi

✅ **Sahi Jawab: B**
> Termux (app) aur Kali Linux (OS) dono environments hain — hacking tools inke andar install karke run kiye jaate hain.

---

**Q4.** "tool basically app/software hi hai" — yeh baat samajhne ke liye sabse acha example kya hai?

- A) tool aur electricity same cheez hain
- B) jaise WhatsApp ek app hai aur ek specific kaam (messaging) karta hai, waise hi hacking tool ek program hai jo ek specific kaam karta hai
- C) tool sirf ek internet connection hota hai
- D) tool ek physical hardware device hota hai jo store se kharidte hain

✅ **Sahi Jawab: B**
> app aur tool ka concept same hai — dono programs hain jo koi khaas kaam karte hain, sirf domain (normal use vs hacking) alag hai.

---

**Q5.** Metasploit ka kaam kya hai (jaisa is topic mein example diya gaya)?

- A) network ka traffic record karna
- B) photos edit karna
- C) vulnerabilities test karna
- D) sirf internet browsing karna

✅ **Sahi Jawab: C**
> Metasploit ek exploitation tool hai jiska kaam vulnerabilities ko test/exploit karna hota hai.

---

**Q6.** agar koi bole "is kaam ke liye ek achha tool use karo" — is line ka matlab kya hai?

- A) ek naya phone khareedo
- B) ek aisa program/software use karo jo specifically yeh kaam karne ke liye bana ho
- C) internet band kar do
- D) Termux delete kar do

✅ **Sahi Jawab: B**
> "tool use karo" ka matlab hota hai ek specific-purpose program/software use karna jo woh particular kaam efficiently kar sake.

---
---

## 📌 Topic 7.2 — Programming Language Kya Hoti Hai Aur Kitne Type Ki Hoti Hain

---

### pehli baat — tool bahut saari programming languages ke hote hain

Topic 7.1 mein humne samjha ki tool ek app/software hai. ab agla sawaal — **yeh app/software banta kaise hai?**

> **har tool kisi na kisi "programming language" mein likha (likha matlab code kiya) gaya hota hai.**

Nmap, Metasploit, Wireshark — yeh sab tools kisi insaan ne baithkar **code likh ke** banaye hain, aur woh code kisi programming language mein likha gaya hota hai. aage jab tum khud tools use karoge, tab yeh samajhna zaroori padega ki woh tool "kis language mein bana hai" — kyunki usi se pata chalta hai woh kaise kaam karta hai, aur zaroorat padne pe usme changes bhi kaise kar sakte ho.

---

### toh programming language hoti kya hai

seedhi baat:

> **Programming language ek tarika hai computer ko instructions dene ka** — jaise hum insaano se Hindi ya English mein baat karte hain, waise hi computer ko "kaam karo" bolne ke liye humein uski samajh aane wali bhasha mein likhna padta hai.

computer khud sirf 0 aur 1 (binary) samajhta hai. lekin insaan ke liye seedha 0-1 mein likhna bahut mushkil hai — isliye programming languages banayi gayi, jo insaano ke liye likhna aasan hai, aur phir woh code computer ke samajhne wali bhasha (binary) mein convert ho jaata hai.

---

### programming languages ke type — 2 tarah se samjho

**1. Compiled vs Interpreted (code kaise chalta hai uske hisaab se)**

| Type | Kaise Kaam Karta Hai | Example Languages |
|---|---|---|
| **Compiled Language** | pura code pehle ek baar mein "compile" hota hai (translate hota hai machine language mein), phir chalta hai | C, C++ |
| **Interpreted Language** | code line-by-line seedha chalaya jaata hai, bina pehle poora translate kiye | Python, JavaScript |

**2. Level ke hisaab se (computer ke kitna paas ya door)**

| Type | Matlab | Example |
|---|---|---|
| **Low-Level Language** | computer/hardware ke bahut paas, samajhna insaan ke liye mushkil | Assembly Language |
| **High-Level Language** | insaan ke liye likhna/samajhna aasan, computer se thoda "door" | Python, JavaScript, C |

---

### hacking mein kaunsi languages sabse zyada kaam aati hain — chhota overview

aage wale tool-chapters mein yeh names baar-baar aayenge, isliye ek chhota overview abhi le lo:

| Language | Kis Kaam Ke Liye Common Hai |
|---|---|
| **Python** | zyada tar hacking tools/scripts isi mein bante hain — automation, scanning tools |
| **Bash** | Linux/Termux/Kali ke andar commands ko chain/automate karne ke liye (jo tumne Chapter 4-6 mein use kiya) |
| **C** | bahut sare core tools (jaise Nmap ka kuch hissa) is mein bane hote hain — fast aur system ke bahut paas |
| **JavaScript** | website/web-app hacking (jaise XSS) samajhne ke liye zaroori |
| **SQL** | database se related attacks (jaise SQL Injection) samajhne ke liye zaroori |

is stage pe yeh saari languages seekhna zaroori nahi hai — sirf itna samajhna hai ki **aage jo bhi tool aayega, uska kaam samajhne ke liye is table ka concept yaad rakhna hai.**

---

### yeh sab jaanna zaroori kyun hai

seedha reason:

> jab aage koi tool seekhoge aur uske andar ka error, code, ya script dikhega — tab "yeh kis language mein hai" pata hona zaroori hai, taaki tum confuse na ho ki yeh code hai ya kuch alag cheez.

isse zyada abhi kuch nahi chahiye — bas itni samajh ke saath ab hum agle chapters mein **asli tools** ki taraf badhenge.

---

### ek line mein

> **Har tool kisi programming language mein likha hota hai. Languages ya toh compiled/interpreted hoti hain ya low-level/high-level. Hacking mein Python, Bash, C, JavaScript, aur SQL sabse zyada common hain — aage ke tools samajhne ke liye yeh naam yaad rakhna kaafi hai.**

---

## 🧠 MCQ Set — Topic 7.2

---

**Q1.** programming language kya hoti hai?

- A) computer ko instructions dene ka tarika, jo insaan ke liye likhna aasan ho
- B) sirf ek app ka naam
- C) ek internet browser
- D) sirf hardware ka part

✅ **Sahi Jawab: A**
> programming language insaan aur computer ke beech ka communication tarika hai — insaan ke liye likhna aasan, computer ke liye samajhna possible.

---

**Q2.** computer khud seedha kya samajhta hai?

- A) Hindi
- B) English
- C) binary (0 aur 1)
- D) sirf Python

✅ **Sahi Jawab: C**
> computer ka core language binary hai — 0 aur 1. programming languages ka code aakhir mein isi mein convert hota hai.

---

**Q3.** Compiled aur Interpreted language mein kya farak hai?

- A) compiled language pehle poora translate hoti hai, interpreted line-by-line chalti hai
- B) dono ek hi cheez hain
- C) interpreted language sirf mobile mein chalti hai
- D) compiled language kabhi nahi chal sakti

✅ **Sahi Jawab: A**
> compiled languages (C, C++) pehle poora compile hoti hain, interpreted languages (Python, JavaScript) line-by-line chalti hain.

---

**Q4.** Low-level aur High-level language mein kya farak hai?

- A) low-level hardware ke paas hoti hai (jaise Assembly), high-level insaan ke likhne/samajhne ke liye aasan hoti hai (jaise Python)
- B) low-level sirf games ke liye hoti hai
- C) high-level language computer samajh hi nahi sakta
- D) dono mein koi farak nahi hai

✅ **Sahi Jawab: A**
> low-level language machine ke bahut paas hoti hai aur samajhna mushkil hota hai, high-level language insaan-friendly hoti hai.

---

**Q5.** hacking tools mein sabse zyada kis language ka use hota hai (jaisa is topic mein bataya gaya)?

- A) sirf Hindi
- B) Python
- C) sirf HTML
- D) koi language use nahi hoti

✅ **Sahi Jawab: B**
> zyada tar hacking scripts/tools Python mein bante hain, kyunki likhna aasan hai aur bahut powerful bhi hai.

---

**Q6.** SQL language kis type ke hacking se sabse zyada connect hai?

- A) database se related attacks jaise SQL Injection
- B) sirf wifi hacking
- C) sirf phone hacking
- D) koi connection nahi hai

✅ **Sahi Jawab: A**
> SQL database ke saath kaam karne ki language hai, isliye SQL Injection jaise attacks samajhne ke liye zaroori hai.

---

**Q7.** yeh chapter mein programming languages ke baare mein itna kyun bataya gaya, agar abhi coding seekhni nahi hai?

- A) taaki aage ke tools ka code/error dekhkar confuse na ho, aur samajh aaye kis language mein tool bana hai
- B) sirf exam pass karne ke liye
- C) kyunki coding seekhna hi is course ka asli maksad hai
- D) koi khaas reason nahi hai

✅ **Sahi Jawab: A**
> is stage pe coding seekhna zaroori nahi, sirf itna samajhna zaroori hai ki tools kis type ki languages mein bante hain — taaki aage confusion na ho.

---

```
════════════════════════════════════════════════════════
   ✅  TOPIC 7.1 COMPLETE — TOOL KYA HOTA HAI
   ✅  TOPIC 7.2 COMPLETE — PROGRAMMING LANGUAGE AUR TYPES
   🎉  CHAPTER 7 COMPLETE — TOOL AUR PROGRAMMING LANGUAGE
════════════════════════════════════════════════════════
```

---
