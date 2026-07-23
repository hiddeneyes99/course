# Chapter 6 — Tool Aur Programming Language — Hacking Ki ABC
### By TWH (Afsar Ali) | Technical White Hat

---

> ## 📱 PHONE TRACK — TERMUX
> Yeh chapter **Termux (Android phone) wale students ke liye** hai.
> Chapter 5 (Mobile Setup) complete karne ke baad yahan aao.

---

## 📚 Table of Contents

| # | Topic | Jump |
|---|---|---|
| 7.1 | Tool Kya Hota Hai — Hacking Ki Duniya Ka Sabse Common Word | [➜ Jao](#-topic-71--tool-kya-hota-hai--hacking-ki-duniya-ka-sabse-common-word) |
| 7.2 | Programming Language Kya Hoti Hai Aur Kitne Type Ki Hoti Hain | [➜ Jao](#-topic-72--programming-language-kya-hoti-hai-aur-kitne-type-ki-hoti-hain) |

---
---

okay guys — pehle ke 5 chapters mein tumne bahut kuch seekh liya hai. computer kaise kaam karta hai, networking kaise chalti hai, Linux ka command-line, aur apne phone pe Termux setup — sab cover ho gaya.

**badhai ho**, kyunki yeh saari neev (foundation) taiyar karna sabse boring lekin sabse zaroori kaam tha, aur tumne woh kar liya.

ab yahan se aage — jo bhi chapters aayenge — unme tum **actual hacking tools** use karna seekhoge (Nmap, Metasploit, Wireshark, aur bhi bahut kuch). lekin usse pehle, ek chhota lekin **bahut zaroori** chapter — jisme sirf 2 cheezein clear karni hain:

1. **"Tool" kehte kise hain** — yeh word ab se tumhari life mein baar-baar aayega.
2. **"Programming Language" kya hoti hai aur kitne type ki hoti hain** — kyunki har tool kisi na kisi language mein hi bana hota hai.

is chapter mein na koi installation hai, na koi command practice — sirf **samajhna** hai. chalo, welcome karte hain **Chapter 6** mein.

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

> **Tool basically ek app ya software hi hota hai** — jaisa tumhare phone mein WhatsApp ek app hai, ya jaisa Termux khud ek app hai, ya jaisa Calculator ek specific kaam (hisaab) karta hai — waise hi hacking ka "tool" bhi ek program hota hai jo **ek specific kaam** karne ke liye banaya gaya hota hai.

example se dekho:

- **Nmap** naam ka tool hai — uska kaam hai network mein devices aur ports dhundna.
- **Wireshark** naam ka tool hai — uska kaam hai network ka traffic dekhna.
- **Metasploit** naam ka tool hai — uska kaam hai vulnerabilities test karna.

teeno "tools" hain, lekin teeno alag-alag kaam karte hain — jaise tumhare phone mein Camera app photo khinchti hai aur Calculator app hisaab karta hai, dono apps hain, kaam alag hai.

---

### toh Termux se tool ka kya connection hai

seedha connection hai:

> **Termux tools "chalane" ki jagah hai — khud tool nahi hai.**

Termux ek app hai jo tumhare Android phone mein Linux jaisa terminal deta hai — **isi ke andar hum yeh tools install karke chalayenge.** matlab Nmap, Hydra, Zphisher jaise tools — yeh sab tumhare phone ke Termux ke andar seedha chal sakte hain.

toh jo bhi tumne Chapter 5 mein seekha (Termux setup, pkg commands) — woh us "ghar" ki tarah hai jahan ab hum "tools" laa kar rakhenge aur use karenge. phone hi tumhara hacking lab hai.

---

### ek line mein

> **Tool ek app/software hi hai, jo ek specific kaam karne ke liye banaya gaya hota hai. Termux woh jagah hai jahan hum apne phone pe yeh tools install karke chalate hain.**

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

**Q3.** Termux ka hacking tools se kya rishta hai?

- A) Termux khud ek hacking tool hai
- B) Termux woh jagah hai jahan hum phone pe tools install karke chalate hain
- C) Termux mein tools kabhi nahi chal sakte — sirf PC pe chalte hain
- D) Termux sirf browsing ke liye hai

✅ **Sahi Jawab: B**
> Termux ek environment hai — hacking tools iske andar install karke phone pe seedha run kiye jaate hain. Phone hi tumhara hacking lab hai.

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

### Compiled vs Interpreted — ab isko poori tarah, deep mein samjho

yeh sabse important concept hai is chapter ka, isliye ismein time lagate hain aur poora andar tak samjhte hain.

pehle yaad karo — computer sirf **binary (0 aur 1)** samajhta hai. jab bhi tum koi code likhte ho (kisi bhi language mein), woh code aakhir mein binary mein hi convert hona padta hai, tabhi computer usko run kar payega. **yeh convert kaise aur kab hota hai** — usi se "compiled" aur "interpreted" ka farak nikalta hai.

---

#### Compiled Language — kaam kaise karta hai, step by step

1. tum apna poora code likhte ho (poora program, ek se lekar aakhri line tak).
2. phir ek special program use hota hai jise **"Compiler"** kehte hain.
3. Compiler tumhare **poore code ko ek hi baar mein** padhta hai, aur usko seedha **machine language (binary)** mein convert kar deta hai — is convert hui file ko usually **".exe" ya binary file** kehte hain.
4. jab bhi tumhe program chalana ho, ab seedha yeh already-converted file chalti hai — computer ko dobara translate karne ki zaroorat nahi padti.

> socho jaise tumne ek poori kitaab (Hindi mein) pehle hi translate karwa kar English mein likh li — ab jab bhi padhni ho, seedha English wali kitaab utha lo, dobara translate karne ki zaroorat nahi.

**fayda:** ek baar compile ho jaane ke baad, program **bahut fast chalta hai** — kyunki translation ka kaam pehle hi ho gaya, chalne ke time koi extra kaam nahi karna padta.

**nuksaan:** agar code mein 1 bhi line galat hui, toh **poora compile fail ho jaata hai** — jab tak error fix na karo, program chal hi nahi sakta. aur agar chhota sa change karna ho, toh dobara poora compile karna padta hai.

**example languages:** **C, C++**

**kahan use hota hai:** operating systems (jaise Linux kernel khud C mein bana hai), games, aur hacking mein woh tools jinko **bahut fast** chalna zaroori hai ya jo hardware ke bahut paas kaam karte hain (jaise exploits, low-level network tools).

---

#### Interpreted Language — kaam kaise karta hai, step by step

1. tum apna code likhte ho.
2. ek special program hota hai jise **"Interpreter"** kehte hain.
3. Interpreter tumhare code ko **line-by-line** padhta hai — pehli line padho, usko turant binary mein convert karke chalao, phir doosri line, phir teesri — aise hi aakhir tak.
4. koi alag se ".exe" file nahi banti — jab bhi chalana ho, interpreter code ko us waqt hi translate karke chalata hai.

> socho jaise ek translator kisi ki speech **live** translate kar raha ho — speaker ek line bolta hai, translator turant uska matlab bata deta hai, phir agli line — ek baar mein poori speech translate karke rakhi nahi hoti.

**fayda:** likhna aur test karna **bahut aasan aur fast** hai — code likho, seedha run karo, dekh lo kaam kar raha hai ya nahi. 1 line change karni ho toh poora dobara "compile" nahi karna padta, seedha phir se run kar do.

**nuksaan:** chalne ki speed compiled language se **thodi slow** hoti hai — kyunki har baar chalte waqt translation bhi sath-sath ho rahi hoti hai.

**example languages:** **Python, JavaScript, Bash/Shell**

**kahan use hota hai:** zyada tar hacking scripts, automation tools, website ka interactive part, aur woh saari jagah jahan **jaldi likhna aur jaldi test karna** zaroori hota hai — isi liye zyada tar hacking tools Python mein milte hain.

---

#### ek table mein side-by-side

| | Compiled Language | Interpreted Language |
|---|---|---|
| **kaam kaise karta hai** | poora code ek baar mein translate hota hai, phir chalta hai | code line-by-line, chalte waqt hi translate hota hai |
| **speed (chalne ki)** | fast | thodi slow |
| **likhna/test karna** | thoda slow — har change ke baad dobara compile | fast — likho aur seedha chalao |
| **error mila toh** | poora program compile hi nahi hoga jab tak fix na ho | jahan tak sahi hai wahan tak chal jaata hai, jis line pe error hai wahi rukega |
| **example** | C, C++ | Python, JavaScript, Bash |
| **hacking mein use** | fast/low-level tools, exploits | scripts, automation, zyada tar tools |

> **yaad rakhne ka tarika:** Compiled = "pehle poora translate, phir chalao" (kitaab translate karwa ke rakhna). Interpreted = "line bolo, turant translate karo" (live translator).

---

### programming languages kitni hoti hain — asli sankhya

seedha jawab — **duniya mein programming languages sainkdo (hundreds) hain**, kayi toh sirf college projects ya research ke liye bani, jo kisi ne suna hi nahi hoga.

lekin tension ki baat nahi — **roz-marra (daily) use hone wali, har jagah milne wali languages sirf 8-10 hi hain.** yehi woh languages hain jo tumhe websites mein, apps mein, tools mein, **har jagah dikhengi.** neeche wahi list hai.

---

### popular programming languages — kahan-kahan use hoti hain

| Language | Compiled ya Interpreted | Kahan Use Hoti Hai |
|---|---|---|
| **Python** | Interpreted | hacking tools/scripts, automation, AI/Machine Learning, data science — **sabse zyada popular hacking ke liye** |
| **JavaScript** | Interpreted | har website ka "interactive" part (buttons, forms, animations) — jahan bhi browser hai, wahan JavaScript hai |
| **C** | Compiled | operating systems (Linux kernel khud C mein bana hai), hardware ke paas wale programs, fast tools |
| **C++** | Compiled | games, heavy software, kuch antivirus/security tools |
| **Java** | Compiled (thoda special — pehle bytecode mein compile hota hai, phir "JVM" naam ka interpreter chalata hai) | Android apps (zyada tar Android apps Java/Kotlin mein bane hain), bade enterprise (company) software |
| **PHP** | Interpreted | bahut saari websites ke "backend" (server side) — WordPress jaisi websites PHP pe chalti hain |
| **SQL** | alag category (Query Language, "programming" se thoda alag) | database se baat karne ke liye — data store/nikaalna, aur SQL Injection attack samajhne ke liye zaroori |
| **Bash / Shell** | Interpreted | Termux ke andar commands chain/automate karna — jo tumne Chapter 4-5 mein khud use kiya |
| **Ruby** | Interpreted | kuch websites (backend), aur ek famous hacking tool **Metasploit** khud Ruby mein bana hai |
| **Go (Golang)** | Compiled | naye zamane ke fast tools, kuch modern hacking/security tools isi mein bante hain |

> is table mein diye gaye 8-10 names hi hain jo aage har chapter mein baar-baar dikhenge — kisi tool ka code dekhoge toh yeh pehchan paoge "yeh Python mein hai" ya "yeh Bash script hai" — bas itna hi target hai abhi.

is stage pe koi bhi language seekhna zaroori nahi hai — sirf itna samajhna hai ki **har tool kisi na kisi language mein bana hota hai, aur upar wali table ke naam sabse zyada milenge.**

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

**Q3.** "Compiler" kaam kya karta hai?

- A) poore code ko ek hi baar mein padhkar seedha machine language (binary) mein convert kar deta hai
- B) code ko line-by-line chalate waqt hi translate karta hai
- C) sirf error dhundta hai, translate nahi karta
- D) internet se code download karta hai

✅ **Sahi Jawab: A**
> Compiler poora code ek baar mein padhta hai aur pehle hi poora translate kar deta hai — jaisa poori kitaab pehle translate karwa lena.

---

**Q4.** "Interpreter" kaam kya karta hai?

- A) code ko line-by-line padhta hai aur turant, chalte waqt hi translate karke run karta hai
- B) poore code ko pehle ek file mein compile kar deta hai
- C) sirf hardware manage karta hai
- D) sirf website design karta hai

✅ **Sahi Jawab: A**
> Interpreter live translator jaisa kaam karta hai — ek line padho, turant translate karo aur chalao, phir agli line.

---

**Q5.** Compiled language ka bada **fayda** kya hai?

- A) likhna bahut aasan hota hai
- B) ek baar compile hone ke baad program bahut fast chalta hai
- C) usmein kabhi error nahi aata
- D) usko internet ki zaroorat nahi padti

✅ **Sahi Jawab: B**
> translation ka kaam pehle hi ho jaata hai, isliye chalne ke waqt extra kaam nahi karna padta — isliye compiled languages fast chalti hain.

---

**Q6.** Interpreted language ka bada **fayda** kya hai (jaisa is topic mein samjhaya gaya)?

- A) likhna aur test karna fast/aasan hota hai — likho aur seedha run kar do
- B) yeh compiled language se hamesha fast chalti hai
- C) isme kabhi error nahi aata
- D) yeh sirf games banane ke liye use hoti hai

✅ **Sahi Jawab: A**
> ek line change karni ho toh poora dobara compile nahi karna — seedha phir se run kar do, isliye likhna/testing fast hota hai.

---

**Q7.** duniya mein programming languages kitni hain, aur roz-marra (daily) kaam aane wali kitni hain (jaisa is topic mein bataya gaya)?

- A) total sirf 2 languages hain
- B) sainkdo (hundreds) languages hain duniya mein, lekin daily/har jagah milne wali sirf 8-10 hi hain
- C) sirf hacking ke liye alag se koi language nahi hoti
- D) sirf 1 hi language hoti hai, baaki sab usi ka naam hai

✅ **Sahi Jawab: B**
> languages sainkdo hain, lekin Python, JavaScript, C, C++, Java, PHP, SQL, Bash, Ruby, Go jaisi 8-10 languages hi sabse zyada common/popular hain.

---

**Q8.** famous hacking tool **Metasploit** kis programming language mein bana hai (jaisa table mein bataya gaya)?

- A) Ruby
- B) HTML
- C) sirf Hindi commands mein
- D) koi language nahi, sirf app hai

✅ **Sahi Jawab: A**
> Metasploit Ruby language mein bana hai — is course mein aage jab Metasploit seekhoge, tab yeh naam yaad rakhna kaam aayega.

---

**Q9.** Java ko "thoda special case" kyun bataya gaya hai compiled/interpreted ki baat mein?

- A) Java na compiled hai na interpreted, koi category nahi hai iski
- B) Java code pehle "bytecode" mein compile hota hai, phir usko JVM naam ka interpreter chalata hai — matlab dono tarike ka mix hai
- C) Java sirf website design ke liye hoti hai
- D) Java sirf mobile mein hi likha ja sakta hai

✅ **Sahi Jawab: B**
> Java pehle bytecode mein compile hoti hai, phir JVM (Java Virtual Machine) us bytecode ko interpret karke chalata hai — isliye yeh dono concepts ka mix hai.

---

**Q10.** yeh chapter mein programming languages ke baare mein itna kyun bataya gaya, agar abhi coding seekhni nahi hai?

- A) taaki aage ke tools ka code/error dekhkar confuse na ho, aur samajh aaye kis language mein tool bana hai
- B) sirf exam pass karne ke liye
- C) kyunki coding seekhna hi is course ka asli maksad hai
- D) koi khaas reason nahi hai

✅ **Sahi Jawab: A**
> is stage pe coding seekhna zaroori nahi, sirf itna samajhna zaroori hai ki tools kis type ki languages mein bante hain — taaki aage confusion na ho.

---

```
════════════════════════════════════════════════════════
   ✅  TOPIC 6.1 COMPLETE — TOOL KYA HOTA HAI
   ✅  TOPIC 6.2 COMPLETE — PROGRAMMING LANGUAGE AUR TYPES
   🎉  CHAPTER 6 COMPLETE — TOOL AUR PROGRAMMING LANGUAGE
   ⬇️  Agle Chapter mein milenge — Chapter 7: Hacking Techniques
════════════════════════════════════════════════════════
```

---
