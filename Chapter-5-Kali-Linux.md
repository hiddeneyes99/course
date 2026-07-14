# Chapter 5 — Kali Linux — Hacker Ka Asli Ghar
### By TWH (Afsar Ali) | Technical White Hat

---

## 📚 Table of Contents

| # | Topic | Jump |
|---|---|---|
| 5.1 | Kali Linux Kya Hai — Poori Kahani | [➜ Jao](#-topic-51--kali-linux-kya-hai--poori-kahani) |
| 5.2 | Kali Linux Kaise Laayein — Installation Methods | [➜ Jao](#-topic-52--kali-linux-kaise-laayein--installation-methods) |
| 5.3 | VirtualBox Pe Kali Install Karna — Step by Step | [➜ Jao](#-topic-53--virtualbox-pe-kali-install-karna--step-by-step) |
| 5.4 | Kali Ka Desktop — Pehli Baar Seedha Dekho | [➜ Jao](#-topic-54--kali-ka-desktop--pehli-baar-seedha-dekho) |
| 5.5 | Terminal Navigation — File System Mein Chalna | [➜ Jao](#-topic-55--terminal-navigation--file-system-mein-chalna) |
| 5.6 | Files Dekhna aur Edit Karna | [➜ Jao](#-topic-56--files-dekhna-aur-edit-karna) |
| 5.7 | Users aur Permissions — Kaun Kya Kar Sakta Hai | [➜ Jao](#-topic-57--users-aur-permissions--kaun-kya-kar-sakta-hai) |
| 5.8 | Networking Commands — Network Ko Terminal Se Dekhna | [➜ Jao](#-topic-58--networking-commands--network-ko-terminal-se-dekhna) |
| 5.9 | Piping aur Redirection — Commands Ko Milao | [➜ Jao](#-topic-59--piping-aur-redirection--commands-ko-milao) |
| 5.10 | Process Management — System Pe Kya Chal Raha Hai | [➜ Jao](#-topic-510--process-management--system-pe-kya-chal-raha-hai) |
| 5.11 | File Search — Kuch Bhi Dhundho | [➜ Jao](#-topic-511--file-search--kuch-bhi-dhundho) |
| 5.12 | Bash Scripting Basics — Terminal Ko Automatic Karo | [➜ Jao](#-topic-512--bash-scripting-basics--terminal-ko-automatic-karo) |

---
---

chapter 4 mein tumne Linux ka background samjha — kya hai, kyun hai, Termux kya hai, aur package manager kaise kaam karta hai.

ab ek baat seedhi —

chapter 4 ek foundation tha. ek introduction tha. ek trailer tha.

**chapter 5 asli film hai.**

kali linux — yeh woh jagah hai jahan ethical hacker actually rehta hai. yahan kaam karta hai. yahan sochta hai. yahan tools chalata hai. aur isliye isko sirf install karke chhod dena kafi nahi — **isko samajhna padega.**

is chapter mein hum kali linux ko bilkul andar se sikhenge. installation se lekar bash scripting tak. koi bhi cheez nahi chhodenge. aur jab yeh chapter khatam hoga — tumhare liye kali linux ek nayi jagah nahi rahegi. **tumhara ghar lagegi.**

chalo shuru karte hain.

---
---

## 📌 Topic 5.1 — Kali Linux Kya Hai — Poori Kahani

---

### chapter 4 mein ek cheez boli thi

chapter 4 mein humne briefly mention kiya tha — Kali Linux ek distro hai jo ethical hackers ke liye banaya gaya hai. 600+ hacking tools pre-installed hain.

ab woh ek line kaafi nahi hai. Kali ko actually samajhna hai — kahaan se aaya, kisne banaya, kyun, versions kya hain, aur officially use karna kaisa lagta hai.

---

### Kali Linux ki kahani

saal tha **2013.**

ek company thi — **Offensive Security** — jo penetration testing aur security research karne wale professionals ki thi.

us waqt ek aur distro tha — **BackTrack Linux.** yeh bhi ethical hacking ke liye tha — lekin problems bahut thi. architecture purana tha. maintenance mushkil tha. packages properly organized nahi the.

Offensive Security ne decide kiya — **BackTrack ko completely rebuild karte hain. scratch se.**

result? **Kali Linux** — March 2013 mein pehli baar release hua.

> **Kali Linux = Offensive Security ka banaya hua, Debian pe based, ethical hacking aur penetration testing ke liye specially designed Linux distribution.**

---

### Debian kya hai — aur Kali uske upar kyun bana?

Debian ek bahut stable aur trusted Linux distro hai. decades se chal raha hai. companies use karte hain servers ke liye.

Kali Linux, Debian ke upar bana hai — matlab Kali ki neev (foundation) Debian ka stable system hai. uske upar Offensive Security ne apna structure rakha — security tools, custom configurations, hacking-specific environment.

ek analogy —

> socho Debian ek strong, reliable imarat ki neev hai. Kali Linux ne us neev ke upar apna ghar banaya — apni zaroorat ke hisaab se. neev strong hai isliye ghar bhi strong hai.

---

### Offensive Security kaun hai?

Offensive Security = woh company jo Kali banati hai aur **OSCP (Offensive Security Certified Professional)** certification deti hai.

OSCP duniya ki sabse respected ethical hacking certification mein se ek hai. Offensive Security real professionals ke liye banaya gaya hai.

Kali Linux free hai — lekin company ke paas expertise genuine hai. inhe ethical hacking mein seriously liya jaata hai globally.

---

### Kali mein kya hota hai pre-installed?

jab tum Kali install karte ho — pehle se hi yeh cheezein hoti hain:

| Category | Examples |
|---|---|
| Network Scanning | Nmap, Masscan |
| Web Testing | Burp Suite, Nikto, SQLmap |
| Password Tools | John the Ripper, Hashcat, Hydra |
| Wireless | Aircrack-ng, Kismet |
| Exploitation | Metasploit Framework |
| Forensics | Autopsy, Volatility |
| Reverse Engineering | Ghidra, Radare2 |
| Sniffing | Wireshark, tcpdump |

yeh sirf examples hain — 600+ tools hain total. **lekin yeh sab aage ke chapters mein cover honge.** is chapter mein sirf Kali Linux itself sikhenge — OS ko, environment ko, commands ko.

---

### Kali Linux ke versions

Kali **rolling release** model follow karta hai — matlab koi fixed "Kali 2.0" ya "Kali 3.0" nahi hota jaise Windows mein hota hai.

har hafte naye updates aate hain. package manager se update karo — latest mil jaata hai. system hamesha updated rehta hai.

lekin **major versions** hote hain — jo design ya features ke liye important hote hain:

| Version | Kab | Kya Naya |
|---|---|---|
| Kali 2013 | March 2013 | BackTrack se replace hua, Debian base |
| Kali 2019 | 2019 | Default user root se badle non-root pe |
| Kali 2020 | 2020 | XFCE default desktop, Win-KeX aaya (WSL ke liye) |
| Kali 2022+ | 2022+ | Purple team tools, cloud integrations |

**ek important change — 2019 mein:**

pehle Kali mein default user `root` tha — matlab seedha admin access. dangerous tha. 2019 ke baad default user normal user hai — `kali` naam ka. root access tabhi lena chahiye jab zaroori ho.

---

### Kali Kaafi Alag Distro Hai — Why?

zyada tar distros **general purpose** hote hain. matlab — office kaam, gaming, browsing, development — sab ek hi distro mein.

Kali **specifically security testing ke liye** hai. isme bahut cheezein hain jo normal use mein zaroori nahi — lekin security professional ke liye daily tool hain.

isliye —

> **agar tumhara daily driver laptop sirf Kali pe ho — yeh sahi nahi. Kali ek specialist tool hai — ek specialist environment ke liye.**

normal use ke liye Ubuntu ya koi aur distro rakho. Kali alag rakho — virtual machine mein ya dedicated machine pe.

---

### Kali Linux aur Law — ek zaroori baat

Kali install karna legal hai. **Kali ka kisi ke system ke against use karna — bina permission ke — illegal hai.**

tool neutral hota hai. use karna aur misuse karna alag hai.

> **ek licensed gun rakhna aur kisi pe chalana — dono alag cheezein hain.**

Kali ek professional tool hai. professional ki tarah use karo.

---

### ek line mein

> **Kali Linux = Offensive Security ka banaya hua, Debian pe based, 600+ security tools ke saath aane wala, ethical hackers ka dedicated OS.**

---

## 🧠 MCQ Set — Topic 5.1

---

**Q1.** Kali Linux kisne banaya?

- A) Offensive Security — BackTrack Linux ki jagah 2013 mein release kiya
- B) Google — Android ke liye bana tha, hackers ne baad mein adopt kiya
- C) Linus Torvalds — Linux kernel ke saath hi bundled security tools include kiye
- D) MIT ke researchers — open source security research project ke tahat

✅ **Sahi Jawab: A**
> Offensive Security ek penetration testing company hai. BackTrack Linux ki limitations ke baad unhone 2013 mein Kali Linux build kiya — scratch se, Debian ke upar.

---

**Q2.** Kali Linux kis Linux distribution pe based hai?

- A) Ubuntu — sabse popular Linux base hai isliye choose kiya gaya
- B) Arch Linux — cutting edge packages ke liye
- C) Debian — stable, reliable, aur long-term support ke liye
- D) Fedora — Red Hat ka enterprise-grade base

✅ **Sahi Jawab: C**
> Kali = Debian pe based. Debian ki stability aur vast package repository pe Offensive Security ne apna security-focused layer rakha.

---

**Q3.** Kali Linux ka "rolling release" model ka matlab kya hai?

- A) har saal ek nayi major version aati hai jise fresh install karna padta hai
- B) ek hi version hoti hai jo roll over nahi hoti — stable rakhne ke liye
- C) Kali free mein roll out hota hai — koi payment nahi kabhi
- D) updates continuously aate rehte hain — koi fixed version nahi, system hamesha latest rehta hai

✅ **Sahi Jawab: D**
> rolling release = har hafte naye updates. `apt update && apt upgrade` se system hamesha current rehta hai. koi major version jump nahi karna padta.

---

**Q4.** 2019 ke baad Kali Linux mein kya important change aaya users ke liye?

- A) default user root se badle normal user `kali` pe — better security practice ke liye
- B) paid subscription shuru ho gaya — tools ke liye license chahiye
- C) GUI hata diya — sirf terminal mode reh gaya
- D) Windows support band kar di — sirf bare metal pe chalega

✅ **Sahi Jawab: A**
> pehle Kali seedha root se start hota tha — risky. 2019 ke baad default user `kali` hai — normal privileges ke saath. root tab use karo jab actually zaroori ho.

---

**Q5.** Kali Linux kyun specifically banaya gaya — general purpose distro kyun nahi?

- A) kyunki general distros mein terminal nahi hota
- B) kyunki security testing ke liye specialized tools, configurations, aur environment chahiye — jo general distros mein nahi hoti
- C) kyunki Kali sirf ARM processors pe chalta hai — jo security hardware use karte hain
- D) kyunki Offensive Security ko ek paid product banana tha — differentiation ke liye

✅ **Sahi Jawab: B**
> Kali mein 600+ pre-installed tools, security-specific configurations, aur penetration testing ke liye optimized environment hai. yeh sab general distros setup mein nahi hote.

---

**Q6.** Kali Linux aur BackTrack Linux mein kya rishta hai?

- A) dono alag companies ke alag products hain — koi connection nahi
- B) BackTrack, Kali ka updated modern version hai — 2020 mein release hua
- C) BackTrack aur Kali same OS hain — sirf naam alag hai different regions ke liye
- D) Kali, BackTrack ka successor hai — same creators ne BackTrack ki limitations ke baad Kali rebuild kiya

✅ **Sahi Jawab: D**
> BackTrack → Kali. same creators (Offensive Security), nayi architecture, Debian base, better maintenance. BackTrack officially 2013 mein retire ho gaya.

---

**Q7.** Kali Linux download aur use karna legally kaisa hai?

- A) illegal — penetration testing tools rakhna India mein banned hai
- B) legal — Kali rakhna allowed hai, lekin bina permission kisi ka system attack karna illegal hai
- C) legal sirf agar tum certified ethical hacker ho — bina certification ke illegal
- D) gray area — laws alag alag deshon mein clear nahi hain Kali ke liye specifically

✅ **Sahi Jawab: B**
> Kali download karna, install karna, seekhna — legal hai. tool ko kisi ke system ke against bina permission use karna — illegal. tool neutral hota hai, intent matter karta hai.

---

**Q8.** Kali Linux mein pre-installed tools kahan se aate hain?

- A) open source security tools hain jo Kali ki team package karke include karti hai
- B) Microsoft aur Google ke certified security tools hain
- C) Kali ki team khud har tool likhti hai — sab in-house developed hain
- D) paid commercial tools hain jo Offensive Security license karke include karti hai

✅ **Sahi Jawab: A**
> Kali mein mostly open source community ke banaye tools hain — Nmap, Metasploit, Wireshark, etc. Kali team inhe package format mein organize karke include karti hai.

---

**Q9.** daily driver laptop pe sirf Kali Linux rakhna kyun sahi nahi?

- A) Kali mein browser nahi hota — internet use nahi ho sakta
- B) Kali mein file save nahi hoti — sab data reboot pe erase hota hai
- C) Kali ke saath warranty void ho jaati hai laptop ki
- D) Kali ek specialist OS hai — daily tasks ke liye nahi banaya gaya, security testing ke liye banaya gaya

✅ **Sahi Jawab: D**
> Kali = specialist tool. ek surgeon apne scalpel se roti nahi kaatta. normal use ke liye Ubuntu ya koi aur distro better hai. Kali alag rakho — VM ya dedicated machine pe.

---

**Q10.** OSCP certification kaun deta hai?

- A) CompTIA — Security+ aur CEH bhi inhi ka hai
- B) EC-Council — Certified Ethical Hacker ka issuer
- C) Offensive Security — Kali Linux ka creator
- D) ISC2 — CISSP aur CCSP ke liye jaane jaate hain

✅ **Sahi Jawab: C**
> Offensive Security = Kali banata hai + OSCP certification deta hai. OSCP duniya ki sabse respected penetration testing certifications mein se ek hai — practical, hands-on exam.

---

**Q11.** Kali Linux mein kitne tools approximately pre-installed aate hain?

- A) 10-20 — sirf most essential tools
- B) 100-150 — common penetration testing tools
- C) 600+ — har category ke liye tools hain
- D) 2000+ — poori security community ke sare tools bundled hain

✅ **Sahi Jawab: C**
> Kali mein 600+ tools hain — network scanning se lekar forensics tak, web testing se lekar wireless attacks tak. har security domain covered hai.

---

**Q12.** Kali Linux ka Debian pe based hone ka kya fayda hai?

- A) Debian ki stability, vast package repository, aur long-term support Kali ko reliable banate hain
- B) Debian ke sare games aur multimedia apps Kali pe automatically available hain
- C) Debian ke users automatically Kali use karna jaante hain — extra learning nahi
- D) Debian ka brand name Kali ko credibility deta hai marketplace mein

✅ **Sahi Jawab: A**
> Debian = proven, stable foundation. decades se servers pe chal raha hai. Kali is stable base ke upar bana — isliye Kali bhi solid hai. Debian ka `apt` package manager bhi use hota hai.

---

**Q13.** Kali Linux mein "Kali" naam kahan se aaya?

- A) founder Kali naam ke developer ke naam pe rakha gaya
- B) "Kali" Hindu goddess Kali se inspired hai — destruction aur power ka symbol — jo Kali Linux ke purpose ko represent karta hai
- C) "K" for Kernel, "A" for Advanced, "L" for Linux, "I" for Interface — acronym hai
- D) BackTrack ka next version "K series" se shuru hona tha — pehla letter K tha

✅ **Sahi Jawab: B**
> Kali Linux ka naam Hindu goddess Kali se inspired hai — jo destruction, transformation aur power ka symbol hai. penetration testing ka nature bhi aisa hi hai — systematically todna taaki better banana ja sake.

---

**Q14.** Kali Linux ka update kaise karte hain?

- A) Kali ki website pe jaao — manual download karo — reinstall karo
- B) `kali-update` — specific command hai Kali ke liye
- C) Offensive Security ka subscription lena padta hai — tab automatic updates milte hain
- D) `sudo apt update && sudo apt upgrade` — Kali rolling release hai, yeh command se hamesha latest rahega

✅ **Sahi Jawab: D**
> rolling release = `apt update && apt upgrade`. chapter 4.3 mein yeh seekha tha. Kali mein same command. hamesha latest rahega bina reinstall ke.

---

**Q15.** Kali Linux kab officially BackTrack ko replace kiya?

- A) 2010 — BackTrack 5 release ke saath hi Kali ka development shuru hua
- B) 2013 — March 2013 mein pehla official release
- C) 2015 — 2 saal development ke baad stable version aaya
- D) 2019 — jab root to non-root default change hua

✅ **Sahi Jawab: B**
> March 2013 — Kali Linux 1.0. BackTrack officially retire. Offensive Security ne completely rebuild kiya — Debian base pe, better architecture ke saath.

---

## 🎯 Task — Topic 5.1 — Kali Linux Ko Explore Karo Bina Install Kiye

**task naam: "Kali se pehli mulaqat"**

Kali install karne se pehle — online dekho kya hota hai andar.

**Step 1 — Kali ki official website dekho:**
```
https://www.kali.org
```
homepage pe download options dekhoge — kitne flavors mein milta hai note karo.

**Step 2 — Tools ki list dekho:**
```
https://www.kali.org/tools/
```
categories dekhoge — web, wireless, forensics, etc. scroll karo — feel karo kitna kuch hai.

**Step 3 — Offensive Security ke baare mein:**
```
https://www.offensive-security.com
```
yeh woh company hai jo Kali banati hai aur OSCP deti hai.

**Socho:**
- kitni categories mein tools hain?
- koi tool ka naam aise tha jo pehle suna ho?
- yeh sab sirf ek OS mein hota hai — yeh realize karo

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.1 COMPLETE — KALI LINUX KI KAHANI
   ⬇️  Neeche hai Topic 5.2
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.2 — Kali Linux Kaise Laayein — Installation Methods

---

### ek sawaal pehle

Kali install karna hai — lekin kaise?

bahut log yahan confused hote hain. "kya main apna laptop format karun?" — nahi! yeh sab se badi galti hogi.

Kali install karne ke **kai tarike hain.** har ek ke apne fayde aur use case hain. pehle samjho — phir decide karo.

---

### Method 1 — Virtual Machine (VM) — Sabse Recommended Beginners Ke Liye

**Virtual Machine kya hoti hai?**

socho tumhare ghar ke andar ek aur chhota sa ghar bana do — plastic ka, fake — lekin sab kuch functionally real. kitchen hai, bathroom hai, rooms hain — lekin asli ghar ke andar.

**yahi virtual machine hai — ek computer ke andar ek aur fake computer.**

tumhara asli computer = **Host**
virtual machine ke andar ka computer = **Guest**

```
Tumhara Laptop (Windows/Mac) ← Host
     └── VirtualBox Software
           └── Kali Linux VM ← Guest
```

**kyun best hai beginners ke liye:**

- ✅ kuch bhi galat hua — VM delete karo, naya banao — host (tumhara laptop) safe
- ✅ ek hi time pe Windows bhi chala sako, Kali bhi chala sako
- ✅ snapshot le sakte ho — galat command chali — undo karo jaise time machine
- ✅ laptop format nahi karna
- ❌ performance thodi slow hogi kyunki resources share hote hain

**VM software options:**

| Software | Price | Recommended For |
|---|---|---|
| **VirtualBox** | Free | Beginners — Windows/Mac/Linux pe |
| **VMware Workstation Player** | Free (basic) | Slightly better performance |
| **VMware Fusion** | Paid (Mac) | Mac users ke liye |
| **UTM** | Free | M1/M2 Mac ke liye |

---

### Method 2 — Live Boot — Bina Install Kiye Chalao

**kya hota hai:**

ek USB drive pe Kali daalo. computer ko us USB se boot karo. Kali chalu ho jaata hai — bilkul asli system ki tarah — **lekin hard disk pe kuch bhi save nahi hoga.** computer band karo — sab wapas.

**use case:**

- quick test karna hai
- install nahi karna
- kisi aur ke computer pe temporarily use karna

**limitation:**
- har baar fresh start — settings, files sab jaati hain
- thoda slow hota hai USB se

---

### Method 3 — Dual Boot — Dono OS ek hi laptop pe

**kya hota hai:**

laptop ki hard disk ko do parts mein divide karo (partition). ek mein Windows, doosre mein Kali. laptop start karte waqt choose karo — kaunsa OS chalana hai.

```
Hard Disk
├── Partition 1 → Windows (100 GB)
└── Partition 2 → Kali Linux (80 GB)

Boot pe:
Choose OS: [Windows] [Kali Linux]
```

**fayde:**
- ✅ full performance — resources share nahi
- ✅ dono OS available

**nuqsaan:**
- ❌ risky — partition galat hua toh data jaata hai
- ❌ ek waqt mein sirf ek OS chalega
- ❌ beginners ke liye setup complex hai

> **beginners ke liye dual boot recommend nahi karta — VM se shuru karo.**

---

### Method 4 — WSL2 (Windows Subsystem for Linux)

Windows 10/11 mein ek feature hai — **WSL2** — jo Windows ke andar directly Linux run karne deta hai.

```
Windows 11
└── WSL2
    └── Kali Linux (terminal based)
```

**kaise enable karein:**

PowerShell mein admin se:
```
wsl --install -d kali-linux
```

restart ke baad Kali terminal mil jaata hai.

**limitation:**
- sirf terminal milta hai — GUI nahi (advanced setup se GUI bhi ho sakta hai lekin complex hai)
- tools ka subset hi kaam karta hai
- networking limitations hain

**use case:** quick commands, lightweight usage — full Kali nahi.

---

### Method 5 — Bare Metal Install — Dedicated Machine

Kali ko directly ek dedicated laptop ya PC pe install karo — koi aur OS nahi.

**perfect for:**
- jab dedicated hacking machine ho
- maximum performance chahiye
- advanced professionals ke liye

**beginners ke liye:** nahi — pehle VM se seekho, phir jab comfortable ho toh dedicated machine consider karo.

---

### Method 6 — Kali Linux on Android (NetHunter)

Offensive Security ka ek project hai — **Kali NetHunter** — jo rooted Android phones pe Kali run karne deta hai.

mobile ethical hacking ke liye — advanced use case. abhi yahan jaana zaroori nahi.

---

### Kali ke Flavors — Download Karte Waqt Kaun Sa Lein?

Kali download karo toh kai options milenge:

| Flavor | Kya Hai | Kiske Liye |
|---|---|---|
| **Kali Linux Installer** | Full install — hard disk pe | Bare metal ya VM |
| **Kali Linux Live** | USB se chalao bina install kiye | Live boot |
| **Kali Linux Virtual Machine** | Pre-built VM file (`.ova`) | VirtualBox/VMware ke liye — sabse easy |
| **Kali Linux WSL** | Windows Store se | WSL users ke liye |
| **Kali Linux NetHunter** | Android ke liye | Mobile hackers |

**beginners ke liye best choice:**

> **"Kali Linux Virtual Machine" — pre-built `.ova` file download karo — VirtualBox mein import karo — 10 minute mein ready.**

yahi hum next topic mein karenge.

---

### Desktop Environments — XFCE, GNOME, KDE?

Kali Linux download karte waqt ek aur choice hoti hai — **Desktop Environment:**

| DE | How It Looks | Resource Usage |
|---|---|---|
| **XFCE** (default) | Lightweight, fast, simple | Low — purane hardware pe bhi chalta hai |
| **GNOME** | Modern, polished | High — zyada RAM chahiye |
| **KDE Plasma** | Feature rich, customizable | Medium-High |

**Kali ka default = XFCE** — beginners ke liye yahi best hai. fast hai, light hai, kaam karta hai.

---

### ek line mein

> **Beginners ke liye: VM mein Kali. Pre-built `.ova` file download karo — VirtualBox mein import karo — ek ghante mein ready. Laptop safe, Kali full power mein.**

---

## 🎯 Task — Topic 5.2 — VirtualBox Download Karo

**task naam: "Kali ke liye ghar tayaar karo"**

abhi Kali install nahi karenge — pehle sirf VirtualBox ready karo.

**Step 1 — VirtualBox download karo:**
```
https://www.virtualbox.org/wiki/Downloads
```
apne OS ke hisaab se download karo — Windows, Mac, ya Linux.

**Step 2 — Install karo:**
- downloaded installer run karo
- "Next, Next, Install" — default settings theek hain
- install complete hone do

**Step 3 — VirtualBox open karo:**
pehli baar khulega — yeh screen dikhegi:
```
Oracle VirtualBox Manager
[New] [Settings] [Start]
```

koi VM nahi hai abhi — blank list hogi. normal hai.

**Step 4 — Note karo:**
Kali ki website pe jaao:
```
https://www.kali.org/get-kali/
```
"Virtual Machines" section dekho — `.ova` file ka size note karo. download time estimate karo apni speed se.

**next topic mein: actual Kali install karenge.**

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.2 COMPLETE — INSTALLATION METHODS
   ⬇️  Neeche hai Topic 5.3
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.3 — VirtualBox Pe Kali Install Karna — Step by Step

---

### ab asli kaam

theory ho gayi. ab Kali actually install karte hain.

yeh topic ek complete step-by-step guide hai. ek ek step follow karo — kuch skip mat karna.

---

### Jo Chahiye

- **VirtualBox** installed (topic 5.2 mein install kiya)
- **Kali Linux Pre-built VM** — `.ova` file
- **Minimum RAM:** 4GB (8GB recommended)
- **Disk Space:** 20-30GB free
- **Internet:** download ke liye

---

### Step 1 — Kali VM File Download Karo

browser mein jaao:
```
https://www.kali.org/get-kali/#kali-virtual-machines
```

"VirtualBox" option pe click karo — `.ova` file download hogi.

file size approximately **3-4 GB** hoti hai. internet speed ke hisaab se 15-60 minute lag sakte hain.

download ke baad — `.ova` file ready hai. kuch install nahi kiya abhi — sirf download hua.

---

### Step 2 — VirtualBox Mein Import Karo

VirtualBox open karo.

menu se: **File → Import Appliance**

```
File → Import Appliance → [.ova file select karo] → Next
```

settings page dikhega — yeh default values theek hain:

| Setting | Default Value | Recommendation |
|---|---|---|
| RAM | 2048 MB (2GB) | 4096 MB (4GB) rakho agar RAM available hai |
| CPU | 1 | 2 rakho agar CPU cores hain |
| Disk | 80 GB | as is |

**RAM adjust karo:** slider pe 4096 MB set karo agar possible hai.

phir: **Import** — 5-10 minute lagenge.

---

### Step 3 — Pehli Baar Start Karo

import complete hua — VM list mein "Kali Linux" dikhega.

**Start** button dabao.

ek nayi window khulegi — Kali boot hoga. pehli baar thoda time lagega — 1-2 minute.

login screen aayega.

---

### Step 4 — Login Karo

Kali ka default username aur password:

```
Username: kali
Password: kali
```

yeh dono type karo — Enter — Kali ka desktop khulega.

---

### Step 5 — Desktop Dekho

XFCE desktop dikhega — taskbar upar ya neeche hoga, application menu hoga.

**pehle kaam — Guest Additions install karo** (VirtualBox specific step):

terminal kholo (taskbar mein terminal icon ya right click → terminal)

```bash
sudo apt update
sudo apt install -y virtualbox-guest-x11
sudo reboot
```

**yeh teen commands ek ek karke samjho:**

**`sudo apt update`**

```
sudo        → "superuser do" — root ki permission se chalao yeh command
              (tumhara normal user account sensitive system changes nahi kar sakta —
               sudo woh permission temporarily deta hai)

apt         → Kali ka package manager — software install/remove/update karta hai
              (poora naam: Advanced Package Tool)

update      → repositories se nayi package list fetch karo
              matlab: internet pe check karo — koi naya software version aaya kya?
              (kuch install nahi hota — sirf list refresh hoti hai)
```

> yeh command pehle hamesha chalanki chahiye — warna outdated list se kaam hota hai.

---

**`sudo apt install -y virtualbox-guest-x11`**

```
sudo                    → root permission se chalao
apt                     → package manager
install                 → yeh software install karo
-y                      → "yes" automatically assume karo
                          (bina iske apt puchega "kya install karein? [Y/n]" — 
                           tumhe manually Y dabaana padega — '-y' woh step skip karta hai)
virtualbox-guest-x11    → package ka naam — yeh hai VirtualBox Guest Additions
                          jo Kali ko sahi size mein dikhata hai, clipboard share karta hai,
                          aur drag-drop enable karta hai
```

---

**`sudo reboot`**

```
sudo     → root permission
reboot   → system restart karo — Guest Additions install ke baad effect aane ke liye
```

reboot ke baad — Kali full screen mein chalega, clipboard share hoga, drag-drop kaam karega.

---

### Step 6 — Password Change Karo

default password "kali" jagah jagah pata hai — badal lo:

```bash
passwd
```

**`passwd` ka matlab:**

```
passwd   → "password" ka short form
           yeh command current user ka password change karta hai
           koi argument nahi chahiye — seedha chalao — interactive prompt aata hai
```

```
Current password: kali           ← purana password verify karega
New password: [apna naya password]
Retype new password: [dobara]    ← confirm karne ke liye
```

**strong password rakho** — numbers, symbols, uppercase — mix karo.

---

### Step 7 — Update Karo

naya system — pehla kaam update:

```bash
sudo apt update && sudo apt upgrade -y
```

**yeh ek line mein kai kaam ho rahe hain — poora breakdown:**

```
sudo          → root permission se chalao
apt           → package manager
update        → repositories se nayi list fetch karo (koi install nahi — sirf list)

&&            → "AND operator" — matlab:
                "pehli command SUCCESS ho — tab aur sirf tab doosri chalao"
                agar 'update' fail ho gaya — 'upgrade' nahi chalega
                yeh safety mechanism hai

sudo          → phir root permission
apt           → phir package manager
upgrade       → jo nayi versions update ne fetch ki thi — unhe actually install karo
                yahan actual download aur install hota hai
-y            → sab upgrade prompts pe automatically "yes" — manually nahi dabaana
```

> **`update` vs `upgrade` ka fark:**
> `update` = sirf list refresh karo — "kya available hai" check karo
> `upgrade` = actually install karo — jo available hai woh download aur update karo
> dono zaruri hain — ek ke bina doosra adhoora hai

yeh thoda time le sakta hai — pehli baar zyada updates hoti hain. chal jaane do.

---

### Step 8 — Snapshot Lo

sab kuch sahi chal raha hai — ab ek snapshot lo. fresh clean state ka.

VirtualBox mein:
```
Machine → Take Snapshot → naam: "Fresh Install - Clean"
```

ab agar kuch bhi galat ho — is snapshot pe wapas aa sakte ho.

---

### Common Problems aur Solutions

**Problem: VM start nahi ho raha — "VT-x is disabled"**

solution: BIOS mein jaao — Virtualization enable karo.
- restart karo, F2/Del/F10 dabao boot pe (manufacturer ke hisaab se alag)
- BIOS mein "Intel Virtualization Technology" ya "AMD-V" dhundho — Enable karo
- save karke exit karo

**Problem: Screen bahut chhoti hai**

solution: Guest Additions install karo (Step 5 mein bataya). phir View → Auto-resize Guest Display.

**Problem: Internet nahi chal raha VM mein**

VirtualBox mein VM settings → Network → Adapter 1:
- Attached to: **NAT** select karo — internet kaam karega

**Problem: Login ke baad kuch nahi dikhta / black screen**

solution: VM restart karo. agar phir bhi — VirtualBox → Display → Video Memory 128 MB karo.

---

### Kali VM Ready — Ab Se Yahi Tumhara Lab Hai

Kali installed hai. Updated hai. Snapshot hua hai.

ab se jab bhi koi topic sikhoge — is Kali VM mein karoge. yahi tumhara safe lab hai — kuch bhi try karo — host laptop safe rahega.

---

## 🎯 Task — Topic 5.3 — Kali Install Karo

**task naam: "apna hacking lab ready karo"**

**Step 1:** `https://www.kali.org/get-kali/#kali-virtual-machines` se `.ova` download karo.

**Step 2:** VirtualBox open karo → File → Import Appliance → `.ova` select karo → RAM 4096 MB set karo → Import.

**Step 3:** Start karo → `kali` / `kali` se login karo.

**Step 4:** terminal kholo, run karo:
```bash
sudo apt update
sudo apt install -y virtualbox-guest-x11
sudo reboot
```

**Step 5:** reboot ke baad:
```bash
passwd
```
password badlo.

**Step 6:**
```bash
sudo apt update && sudo apt upgrade -y
```
update complete hone do.

**Step 7:** VirtualBox → Machine → Take Snapshot → naam: "Clean Install"

**Verify karo:**
```bash
uname -a
```
Kali ka version aur kernel dikhega. Kali ready hai. 🎉

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.3 COMPLETE — KALI INSTALL READY
   ⬇️  Neeche hai Topic 5.4
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.4 — Kali Ka Desktop — Pehli Baar Seedha Dekho

---

### pehli baar khologe toh overwhelm hoga — normal hai

Kali ka desktop khula. ek bahut kuch dikh raha hai. taskbar, icons, menu — aur tum soch rahe ho "yeh sab kya hai?"

normal hai. har kisi ke saath aise hi hua.

ab hum ek ek cheez seedha samjhenge. koi panic nahi.

---

### XFCE Desktop — Kali Ka Default Interface

Kali mein XFCE desktop environment hota hai. yeh Windows ya Android jaisa nahi lagta — alag hai. lekin kuch minutes mein comfortable ho jaoge.

```
┌─────────────────────────────────────────────────────────┐
│  [Applications ▼]  [Places ▼]  [System ▼]          🔋🕐 │  ← Top Panel
├─────────────────────────────────────────────────────────┤
│                                                         │
│                                                         │
│              (Desktop Area)                             │
│                                                         │
│                                                         │
├─────────────────────────────────────────────────────────┤
│  [🖥️ Terminal] [🌐 Browser]  ...          [Workspaces]  │  ← Bottom Panel (ya top pe)
└─────────────────────────────────────────────────────────┘
```

---

### Top Panel — Kya Hai Kya?

**Applications menu:**
yahan sare installed programs hain — categories mein:

```
Applications
├── 01 - Information Gathering    ← network/target info tools
├── 02 - Vulnerability Analysis   ← vulnerability scanners
├── 03 - Web Application Analysis ← web hacking tools
├── 04 - Database Assessment      ← database tools
├── 05 - Password Attacks         ← password tools
├── 06 - Wireless Attacks         ← WiFi tools
├── 07 - Reverse Engineering      ← RE tools
├── 08 - Exploitation Tools       ← exploit tools
├── 09 - Sniffing & Spoofing      ← traffic tools
├── 10 - Post Exploitation        ← after getting in
├── 11 - Forensics                ← digital forensics
├── 12 - Reporting Tools          ← report banane ke liye
└── Usual Apps                    ← browser, file manager, etc.
```

yeh categories — ethical hacking ka workflow hai. pehle information gather karo, phir vulnerabilities dhundho, phir exploit karo. numbers order mein hain.

**Places menu:**
- Home, Desktop, Downloads — file system navigate karne ke liye

**System menu:**
- Settings, Log Out, Shut Down

---

### Terminal — Sabse Important Application

Kali mein terminal **sabse zyada use hone wali cheez** hai.

terminal kholne ke teen tarike:

1. **Keyboard shortcut:** `Ctrl + Alt + T`
2. **Taskbar pe terminal icon:** click karo
3. **Right click** desktop pe → Open Terminal

terminal khulne par yeh dikhega:

```
┌──(kali㉿kali)-[~]
└─$
```

yeh Kali ka prompt hai. breakdown:

```
┌──(kali㉿kali)-[~]
       │    │    │
       │    │    └── [~] = current location (~ = home directory)
       │    └────── kali = machine name (hostname)
       └─────────── kali = current username
└─$               = command type karne ki jagah
```

---

### File Manager — Thunar

Kali mein File Manager ka naam **Thunar** hai.

kholne ke liye: Places → Home Folder

ya terminal mein:
```bash
thunar
```

yahan files aur folders Windows Explorer jaisi dikhti hain. lekin hum mostly terminal se kaam karenge — GUI sirf reference ke liye.

---

### Text Editor — Mousepad

simple text files khol ke dekhne ke liye Kali mein **Mousepad** editor hai.

kholne ke liye: Applications → Accessories → Mousepad

ya terminal se:
```bash
mousepad filename.txt
```

---

### Web Browser — Firefox ESR

Kali mein default browser **Firefox ESR** aata hai.

ESR = Extended Support Release — stable version.

browser se kali.org, documentation, aur web-based tools access kar sakte ho.

---

### Workspaces — Kali Ki Super Power

XFCE mein ek feature hai — **Multiple Workspaces.**

socho multiple virtual desktops — ek pe terminal chal raha hai, ek pe browser, ek pe file manager — sab alag screens pe.

```
Workspace 1 → Terminal chala raha hai
Workspace 2 → Browser aur notes
Workspace 3 → Koi tool chal raha hai
```

switch karna: `Ctrl + F1`, `Ctrl + F2`, `Ctrl + F3` — ya taskbar mein workspace switcher.

professional log yeh use karte hain — work organized rehta hai.

---

### Right Click — Desktop Pe

desktop pe right click karo — menu aayega:

```
Open Terminal Here
Create Folder
Create Document
...
```

"Open Terminal Here" — bahut useful hai. jis folder mein ho — wahan se seedha terminal khulega.

---

### System Settings

Applications → Settings → Settings Manager — yahan sab kuch customize kar sakte ho:
- display resolution
- keyboard shortcuts
- mouse settings
- appearance / themes

---

### Kali Ka Wallpaper — Woh Dragon

Kali ka default wallpaper ek dragon hai — Kali Linux ka logo. XFCE aur GNOME mein alag alag design hote hain lekin dragon icon consistent hai.

---

### Shortcut Keys — Yaad Rakho

| Shortcut | Kaam |
|---|---|
| `Ctrl + Alt + T` | Terminal kholna |
| `Ctrl + F1` / `F2` / `F3` | Workspace switch |
| `Alt + F4` | Current window band karna |
| `Alt + Tab` | Windows ke beech switch |
| `Super` (Windows key) | Application launcher |
| `Ctrl + C` | Running command rokna |
| `Ctrl + L` | Terminal clear karna |

---

### ek line mein

> **Kali ka desktop alag lagta hai — lekin simple hai. Terminal sabse important jagah hai. Baki GUI sirf support ke liye hai.**

---

## 🧠 MCQ Set — Topic 5.4

---

**Q1.** Kali mein terminal kholne ka keyboard shortcut kya hai?

- A) `Ctrl + T`
- B) `Alt + T`
- C) `Ctrl + Alt + T`
- D) `Super + Enter`

✅ **Sahi Jawab: C**
> `Ctrl + Alt + T` — yeh shortcut yaad rakho. Kali pe sabse zyada use hone wala shortcut hai — terminal kholna. har kaam yahan se shuru hota hai.

---

**Q2.** Kali ke terminal prompt mein `[~]` ka matlab kya hai?

- A) root directory — `/` pe ho
- B) system directory — `/etc` pe ho
- C) temp directory — `/tmp` pe ho
- D) home directory — current user ka home folder

✅ **Sahi Jawab: D**
> `~` = tilde = home directory shortcut. `kali` user ke liye `~` matlab `/home/kali`. jab bhi `~` dekho — home folder pe ho.

---

**Q3.** Kali ke Applications menu mein categories numbered (01, 02, 03...) kyun hain?

- A) ethical hacking ka workflow represent karta hai — information gathering pehle, exploitation baad mein
- B) tools ka alphabetical order maintain karne ke liye — numbers sort karte hain
- C) Offensive Security ka internal tool numbering system hai — support ke liye
- D) numbers difficulty level batate hain — 01 easy, 12 hardest

✅ **Sahi Jawab: A**
> categories ka order = hacking workflow. 01 Information Gathering se shuru, phir Vulnerability Analysis, phir Exploitation — yeh actual penetration testing process hai. soch ke design kiya gaya hai.

---

**Q4.** XFCE mein "Workspaces" kya hote hain?

- A) alag alag user accounts — har workspace ek alag user ke liye
- B) multiple virtual desktops — alag alag windows alag alag screens pe organized
- C) VirtualBox ke andar alag environments — har workspace ek VM
- D) saved terminal sessions — band hone pe automatically restore hote hain

✅ **Sahi Jawab: B**
> workspaces = virtual desktops. workspace 1 pe terminal, workspace 2 pe browser — switch karo `Ctrl+F1/F2`. professional Kali users always multiple workspaces use karte hain.

---

**Q5.** Kali terminal prompt `┌──(kali㉿kali)-[~]` mein `㉿` ke dono taraf kya hai?

- A) left = machine name, right = username
- B) left = OS version, right = kernel version
- C) left = directory, right = user permissions
- D) left = username, right = hostname (machine name)

✅ **Sahi Jawab: D**
> format hai `username㉿hostname`. `kali㉿kali` matlab username=kali, hostname=kali. agar tum hostname change karo — right wala badlega.

---

**Q6.** Kali mein `$` prompt ka matlab kya hai?

- A) normal user mode — root nahi ho — regular user ke saath kaam kar rahe ho
- B) dollar sign = paid features available hain
- C) script mode — normal command mode nahi
- D) error state — kuch galat tha pichli command mein

✅ **Sahi Jawab: A**
> `# Chapter 5 — Kali Linux — Hacker Ka Asli Ghar
### By TWH (Afsar Ali) | Technical White Hat

---

## 📚 Table of Contents

| # | Topic | Jump |
|---|---|---|
| 5.1 | Kali Linux Kya Hai — Poori Kahani | [➜ Jao](#-topic-51--kali-linux-kya-hai--poori-kahani) |
| 5.2 | Kali Linux Kaise Laayein — Installation Methods | [➜ Jao](#-topic-52--kali-linux-kaise-laayein--installation-methods) |
| 5.3 | VirtualBox Pe Kali Install Karna — Step by Step | [➜ Jao](#-topic-53--virtualbox-pe-kali-install-karna--step-by-step) |
| 5.4 | Kali Ka Desktop — Pehli Baar Seedha Dekho | [➜ Jao](#-topic-54--kali-ka-desktop--pehli-baar-seedha-dekho) |
| 5.5 | Terminal Navigation — File System Mein Chalna | [➜ Jao](#-topic-55--terminal-navigation--file-system-mein-chalna) |
| 5.6 | Files Dekhna aur Edit Karna | [➜ Jao](#-topic-56--files-dekhna-aur-edit-karna) |
| 5.7 | Users aur Permissions — Kaun Kya Kar Sakta Hai | [➜ Jao](#-topic-57--users-aur-permissions--kaun-kya-kar-sakta-hai) |
| 5.8 | Networking Commands — Network Ko Terminal Se Dekhna | [➜ Jao](#-topic-58--networking-commands--network-ko-terminal-se-dekhna) |
| 5.9 | Piping aur Redirection — Commands Ko Milao | [➜ Jao](#-topic-59--piping-aur-redirection--commands-ko-milao) |
| 5.10 | Process Management — System Pe Kya Chal Raha Hai | [➜ Jao](#-topic-510--process-management--system-pe-kya-chal-raha-hai) |
| 5.11 | File Search — Kuch Bhi Dhundho | [➜ Jao](#-topic-511--file-search--kuch-bhi-dhundho) |
| 5.12 | Bash Scripting Basics — Terminal Ko Automatic Karo | [➜ Jao](#-topic-512--bash-scripting-basics--terminal-ko-automatic-karo) |

---
---

chapter 4 mein tumne Linux ka background samjha — kya hai, kyun hai, Termux kya hai, aur package manager kaise kaam karta hai.

ab ek baat seedhi —

chapter 4 ek foundation tha. ek introduction tha. ek trailer tha.

**chapter 5 asli film hai.**

kali linux — yeh woh jagah hai jahan ethical hacker actually rehta hai. yahan kaam karta hai. yahan sochta hai. yahan tools chalata hai. aur isliye isko sirf install karke chhod dena kafi nahi — **isko samajhna padega.**

is chapter mein hum kali linux ko bilkul andar se sikhenge. installation se lekar bash scripting tak. koi bhi cheez nahi chhodenge. aur jab yeh chapter khatam hoga — tumhare liye kali linux ek nayi jagah nahi rahegi. **tumhara ghar lagegi.**

chalo shuru karte hain.

---
---

## 📌 Topic 5.1 — Kali Linux Kya Hai — Poori Kahani

---

### chapter 4 mein ek cheez boli thi

chapter 4 mein humne briefly mention kiya tha — Kali Linux ek distro hai jo ethical hackers ke liye banaya gaya hai. 600+ hacking tools pre-installed hain.

ab woh ek line kaafi nahi hai. Kali ko actually samajhna hai — kahaan se aaya, kisne banaya, kyun, versions kya hain, aur officially use karna kaisa lagta hai.

---

### Kali Linux ki kahani

saal tha **2013.**

ek company thi — **Offensive Security** — jo penetration testing aur security research karne wale professionals ki thi.

us waqt ek aur distro tha — **BackTrack Linux.** yeh bhi ethical hacking ke liye tha — lekin problems bahut thi. architecture purana tha. maintenance mushkil tha. packages properly organized nahi the.

Offensive Security ne decide kiya — **BackTrack ko completely rebuild karte hain. scratch se.**

result? **Kali Linux** — March 2013 mein pehli baar release hua.

> **Kali Linux = Offensive Security ka banaya hua, Debian pe based, ethical hacking aur penetration testing ke liye specially designed Linux distribution.**

---

### Debian kya hai — aur Kali uske upar kyun bana?

Debian ek bahut stable aur trusted Linux distro hai. decades se chal raha hai. companies use karte hain servers ke liye.

Kali Linux, Debian ke upar bana hai — matlab Kali ki neev (foundation) Debian ka stable system hai. uske upar Offensive Security ne apna structure rakha — security tools, custom configurations, hacking-specific environment.

ek analogy —

> socho Debian ek strong, reliable imarat ki neev hai. Kali Linux ne us neev ke upar apna ghar banaya — apni zaroorat ke hisaab se. neev strong hai isliye ghar bhi strong hai.

---

### Offensive Security kaun hai?

Offensive Security = woh company jo Kali banati hai aur **OSCP (Offensive Security Certified Professional)** certification deti hai.

OSCP duniya ki sabse respected ethical hacking certification mein se ek hai. Offensive Security real professionals ke liye banaya gaya hai.

Kali Linux free hai — lekin company ke paas expertise genuine hai. inhe ethical hacking mein seriously liya jaata hai globally.

---

### Kali mein kya hota hai pre-installed?

jab tum Kali install karte ho — pehle se hi yeh cheezein hoti hain:

| Category | Examples |
|---|---|
| Network Scanning | Nmap, Masscan |
| Web Testing | Burp Suite, Nikto, SQLmap |
| Password Tools | John the Ripper, Hashcat, Hydra |
| Wireless | Aircrack-ng, Kismet |
| Exploitation | Metasploit Framework |
| Forensics | Autopsy, Volatility |
| Reverse Engineering | Ghidra, Radare2 |
| Sniffing | Wireshark, tcpdump |

yeh sirf examples hain — 600+ tools hain total. **lekin yeh sab aage ke chapters mein cover honge.** is chapter mein sirf Kali Linux itself sikhenge — OS ko, environment ko, commands ko.

---

### Kali Linux ke versions

Kali **rolling release** model follow karta hai — matlab koi fixed "Kali 2.0" ya "Kali 3.0" nahi hota jaise Windows mein hota hai.

har hafte naye updates aate hain. package manager se update karo — latest mil jaata hai. system hamesha updated rehta hai.

lekin **major versions** hote hain — jo design ya features ke liye important hote hain:

| Version | Kab | Kya Naya |
|---|---|---|
| Kali 2013 | March 2013 | BackTrack se replace hua, Debian base |
| Kali 2019 | 2019 | Default user root se badle non-root pe |
| Kali 2020 | 2020 | XFCE default desktop, Win-KeX aaya (WSL ke liye) |
| Kali 2022+ | 2022+ | Purple team tools, cloud integrations |

**ek important change — 2019 mein:**

pehle Kali mein default user `root` tha — matlab seedha admin access. dangerous tha. 2019 ke baad default user normal user hai — `kali` naam ka. root access tabhi lena chahiye jab zaroori ho.

---

### Kali Kaafi Alag Distro Hai — Why?

zyada tar distros **general purpose** hote hain. matlab — office kaam, gaming, browsing, development — sab ek hi distro mein.

Kali **specifically security testing ke liye** hai. isme bahut cheezein hain jo normal use mein zaroori nahi — lekin security professional ke liye daily tool hain.

isliye —

> **agar tumhara daily driver laptop sirf Kali pe ho — yeh sahi nahi. Kali ek specialist tool hai — ek specialist environment ke liye.**

normal use ke liye Ubuntu ya koi aur distro rakho. Kali alag rakho — virtual machine mein ya dedicated machine pe.

---

### Kali Linux aur Law — ek zaroori baat

Kali install karna legal hai. **Kali ka kisi ke system ke against use karna — bina permission ke — illegal hai.**

tool neutral hota hai. use karna aur misuse karna alag hai.

> **ek licensed gun rakhna aur kisi pe chalana — dono alag cheezein hain.**

Kali ek professional tool hai. professional ki tarah use karo.

---

### ek line mein

> **Kali Linux = Offensive Security ka banaya hua, Debian pe based, 600+ security tools ke saath aane wala, ethical hackers ka dedicated OS.**

---

## 🧠 MCQ Set — Topic 5.1

---

**Q1.** Kali Linux kisne banaya?

- A) Offensive Security — BackTrack Linux ki jagah 2013 mein release kiya
- B) Google — Android ke liye bana tha, hackers ne baad mein adopt kiya
- C) Linus Torvalds — Linux kernel ke saath hi bundled security tools include kiye
- D) MIT ke researchers — open source security research project ke tahat

✅ **Sahi Jawab: A**
> Offensive Security ek penetration testing company hai. BackTrack Linux ki limitations ke baad unhone 2013 mein Kali Linux build kiya — scratch se, Debian ke upar.

---

**Q2.** Kali Linux kis Linux distribution pe based hai?

- A) Ubuntu — sabse popular Linux base hai isliye choose kiya gaya
- B) Arch Linux — cutting edge packages ke liye
- C) Debian — stable, reliable, aur long-term support ke liye
- D) Fedora — Red Hat ka enterprise-grade base

✅ **Sahi Jawab: C**
> Kali = Debian pe based. Debian ki stability aur vast package repository pe Offensive Security ne apna security-focused layer rakha.

---

**Q3.** Kali Linux ka "rolling release" model ka matlab kya hai?

- A) har saal ek nayi major version aati hai jise fresh install karna padta hai
- B) ek hi version hoti hai jo roll over nahi hoti — stable rakhne ke liye
- C) Kali free mein roll out hota hai — koi payment nahi kabhi
- D) updates continuously aate rehte hain — koi fixed version nahi, system hamesha latest rehta hai

✅ **Sahi Jawab: D**
> rolling release = har hafte naye updates. `apt update && apt upgrade` se system hamesha current rehta hai. koi major version jump nahi karna padta.

---

**Q4.** 2019 ke baad Kali Linux mein kya important change aaya users ke liye?

- A) default user root se badle normal user `kali` pe — better security practice ke liye
- B) paid subscription shuru ho gaya — tools ke liye license chahiye
- C) GUI hata diya — sirf terminal mode reh gaya
- D) Windows support band kar di — sirf bare metal pe chalega

✅ **Sahi Jawab: A**
> pehle Kali seedha root se start hota tha — risky. 2019 ke baad default user `kali` hai — normal privileges ke saath. root tab use karo jab actually zaroori ho.

---

**Q5.** Kali Linux kyun specifically banaya gaya — general purpose distro kyun nahi?

- A) kyunki general distros mein terminal nahi hota
- B) kyunki security testing ke liye specialized tools, configurations, aur environment chahiye — jo general distros mein nahi hoti
- C) kyunki Kali sirf ARM processors pe chalta hai — jo security hardware use karte hain
- D) kyunki Offensive Security ko ek paid product banana tha — differentiation ke liye

✅ **Sahi Jawab: B**
> Kali mein 600+ pre-installed tools, security-specific configurations, aur penetration testing ke liye optimized environment hai. yeh sab general distros setup mein nahi hote.

---

**Q6.** Kali Linux aur BackTrack Linux mein kya rishta hai?

- A) dono alag companies ke alag products hain — koi connection nahi
- B) BackTrack, Kali ka updated modern version hai — 2020 mein release hua
- C) BackTrack aur Kali same OS hain — sirf naam alag hai different regions ke liye
- D) Kali, BackTrack ka successor hai — same creators ne BackTrack ki limitations ke baad Kali rebuild kiya

✅ **Sahi Jawab: D**
> BackTrack → Kali. same creators (Offensive Security), nayi architecture, Debian base, better maintenance. BackTrack officially 2013 mein retire ho gaya.

---

**Q7.** Kali Linux download aur use karna legally kaisa hai?

- A) illegal — penetration testing tools rakhna India mein banned hai
- B) legal — Kali rakhna allowed hai, lekin bina permission kisi ka system attack karna illegal hai
- C) legal sirf agar tum certified ethical hacker ho — bina certification ke illegal
- D) gray area — laws alag alag deshon mein clear nahi hain Kali ke liye specifically

✅ **Sahi Jawab: B**
> Kali download karna, install karna, seekhna — legal hai. tool ko kisi ke system ke against bina permission use karna — illegal. tool neutral hota hai, intent matter karta hai.

---

**Q8.** Kali Linux mein pre-installed tools kahan se aate hain?

- A) open source security tools hain jo Kali ki team package karke include karti hai
- B) Microsoft aur Google ke certified security tools hain
- C) Kali ki team khud har tool likhti hai — sab in-house developed hain
- D) paid commercial tools hain jo Offensive Security license karke include karti hai

✅ **Sahi Jawab: A**
> Kali mein mostly open source community ke banaye tools hain — Nmap, Metasploit, Wireshark, etc. Kali team inhe package format mein organize karke include karti hai.

---

**Q9.** daily driver laptop pe sirf Kali Linux rakhna kyun sahi nahi?

- A) Kali mein browser nahi hota — internet use nahi ho sakta
- B) Kali mein file save nahi hoti — sab data reboot pe erase hota hai
- C) Kali ke saath warranty void ho jaati hai laptop ki
- D) Kali ek specialist OS hai — daily tasks ke liye nahi banaya gaya, security testing ke liye banaya gaya

✅ **Sahi Jawab: D**
> Kali = specialist tool. ek surgeon apne scalpel se roti nahi kaatta. normal use ke liye Ubuntu ya koi aur distro better hai. Kali alag rakho — VM ya dedicated machine pe.

---

**Q10.** OSCP certification kaun deta hai?

- A) CompTIA — Security+ aur CEH bhi inhi ka hai
- B) EC-Council — Certified Ethical Hacker ka issuer
- C) Offensive Security — Kali Linux ka creator
- D) ISC2 — CISSP aur CCSP ke liye jaane jaate hain

✅ **Sahi Jawab: C**
> Offensive Security = Kali banata hai + OSCP certification deta hai. OSCP duniya ki sabse respected penetration testing certifications mein se ek hai — practical, hands-on exam.

---

**Q11.** Kali Linux mein kitne tools approximately pre-installed aate hain?

- A) 10-20 — sirf most essential tools
- B) 100-150 — common penetration testing tools
- C) 600+ — har category ke liye tools hain
- D) 2000+ — poori security community ke sare tools bundled hain

✅ **Sahi Jawab: C**
> Kali mein 600+ tools hain — network scanning se lekar forensics tak, web testing se lekar wireless attacks tak. har security domain covered hai.

---

**Q12.** Kali Linux ka Debian pe based hone ka kya fayda hai?

- A) Debian ki stability, vast package repository, aur long-term support Kali ko reliable banate hain
- B) Debian ke sare games aur multimedia apps Kali pe automatically available hain
- C) Debian ke users automatically Kali use karna jaante hain — extra learning nahi
- D) Debian ka brand name Kali ko credibility deta hai marketplace mein

✅ **Sahi Jawab: A**
> Debian = proven, stable foundation. decades se servers pe chal raha hai. Kali is stable base ke upar bana — isliye Kali bhi solid hai. Debian ka `apt` package manager bhi use hota hai.

---

**Q13.** Kali Linux mein "Kali" naam kahan se aaya?

- A) founder Kali naam ke developer ke naam pe rakha gaya
- B) "Kali" Hindu goddess Kali se inspired hai — destruction aur power ka symbol — jo Kali Linux ke purpose ko represent karta hai
- C) "K" for Kernel, "A" for Advanced, "L" for Linux, "I" for Interface — acronym hai
- D) BackTrack ka next version "K series" se shuru hona tha — pehla letter K tha

✅ **Sahi Jawab: B**
> Kali Linux ka naam Hindu goddess Kali se inspired hai — jo destruction, transformation aur power ka symbol hai. penetration testing ka nature bhi aisa hi hai — systematically todna taaki better banana ja sake.

---

**Q14.** Kali Linux ka update kaise karte hain?

- A) Kali ki website pe jaao — manual download karo — reinstall karo
- B) `kali-update` — specific command hai Kali ke liye
- C) Offensive Security ka subscription lena padta hai — tab automatic updates milte hain
- D) `sudo apt update && sudo apt upgrade` — Kali rolling release hai, yeh command se hamesha latest rahega

✅ **Sahi Jawab: D**
> rolling release = `apt update && apt upgrade`. chapter 4.3 mein yeh seekha tha. Kali mein same command. hamesha latest rahega bina reinstall ke.

---

**Q15.** Kali Linux kab officially BackTrack ko replace kiya?

- A) 2010 — BackTrack 5 release ke saath hi Kali ka development shuru hua
- B) 2013 — March 2013 mein pehla official release
- C) 2015 — 2 saal development ke baad stable version aaya
- D) 2019 — jab root to non-root default change hua

✅ **Sahi Jawab: B**
> March 2013 — Kali Linux 1.0. BackTrack officially retire. Offensive Security ne completely rebuild kiya — Debian base pe, better architecture ke saath.

---

## 🎯 Task — Topic 5.1 — Kali Linux Ko Explore Karo Bina Install Kiye

**task naam: "Kali se pehli mulaqat"**

Kali install karne se pehle — online dekho kya hota hai andar.

**Step 1 — Kali ki official website dekho:**
```
https://www.kali.org
```
homepage pe download options dekhoge — kitne flavors mein milta hai note karo.

**Step 2 — Tools ki list dekho:**
```
https://www.kali.org/tools/
```
categories dekhoge — web, wireless, forensics, etc. scroll karo — feel karo kitna kuch hai.

**Step 3 — Offensive Security ke baare mein:**
```
https://www.offensive-security.com
```
yeh woh company hai jo Kali banati hai aur OSCP deti hai.

**Socho:**
- kitni categories mein tools hain?
- koi tool ka naam aise tha jo pehle suna ho?
- yeh sab sirf ek OS mein hota hai — yeh realize karo

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.1 COMPLETE — KALI LINUX KI KAHANI
   ⬇️  Neeche hai Topic 5.2
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.2 — Kali Linux Kaise Laayein — Installation Methods

---

### ek sawaal pehle

Kali install karna hai — lekin kaise?

bahut log yahan confused hote hain. "kya main apna laptop format karun?" — nahi! yeh sab se badi galti hogi.

Kali install karne ke **kai tarike hain.** har ek ke apne fayde aur use case hain. pehle samjho — phir decide karo.

---

### Method 1 — Virtual Machine (VM) — Sabse Recommended Beginners Ke Liye

**Virtual Machine kya hoti hai?**

socho tumhare ghar ke andar ek aur chhota sa ghar bana do — plastic ka, fake — lekin sab kuch functionally real. kitchen hai, bathroom hai, rooms hain — lekin asli ghar ke andar.

**yahi virtual machine hai — ek computer ke andar ek aur fake computer.**

tumhara asli computer = **Host**
virtual machine ke andar ka computer = **Guest**

```
Tumhara Laptop (Windows/Mac) ← Host
     └── VirtualBox Software
           └── Kali Linux VM ← Guest
```

**kyun best hai beginners ke liye:**

- ✅ kuch bhi galat hua — VM delete karo, naya banao — host (tumhara laptop) safe
- ✅ ek hi time pe Windows bhi chala sako, Kali bhi chala sako
- ✅ snapshot le sakte ho — galat command chali — undo karo jaise time machine
- ✅ laptop format nahi karna
- ❌ performance thodi slow hogi kyunki resources share hote hain

**VM software options:**

| Software | Price | Recommended For |
|---|---|---|
| **VirtualBox** | Free | Beginners — Windows/Mac/Linux pe |
| **VMware Workstation Player** | Free (basic) | Slightly better performance |
| **VMware Fusion** | Paid (Mac) | Mac users ke liye |
| **UTM** | Free | M1/M2 Mac ke liye |

---

### Method 2 — Live Boot — Bina Install Kiye Chalao

**kya hota hai:**

ek USB drive pe Kali daalo. computer ko us USB se boot karo. Kali chalu ho jaata hai — bilkul asli system ki tarah — **lekin hard disk pe kuch bhi save nahi hoga.** computer band karo — sab wapas.

**use case:**

- quick test karna hai
- install nahi karna
- kisi aur ke computer pe temporarily use karna

**limitation:**
- har baar fresh start — settings, files sab jaati hain
- thoda slow hota hai USB se

---

### Method 3 — Dual Boot — Dono OS ek hi laptop pe

**kya hota hai:**

laptop ki hard disk ko do parts mein divide karo (partition). ek mein Windows, doosre mein Kali. laptop start karte waqt choose karo — kaunsa OS chalana hai.

```
Hard Disk
├── Partition 1 → Windows (100 GB)
└── Partition 2 → Kali Linux (80 GB)

Boot pe:
Choose OS: [Windows] [Kali Linux]
```

**fayde:**
- ✅ full performance — resources share nahi
- ✅ dono OS available

**nuqsaan:**
- ❌ risky — partition galat hua toh data jaata hai
- ❌ ek waqt mein sirf ek OS chalega
- ❌ beginners ke liye setup complex hai

> **beginners ke liye dual boot recommend nahi karta — VM se shuru karo.**

---

### Method 4 — WSL2 (Windows Subsystem for Linux)

Windows 10/11 mein ek feature hai — **WSL2** — jo Windows ke andar directly Linux run karne deta hai.

```
Windows 11
└── WSL2
    └── Kali Linux (terminal based)
```

**kaise enable karein:**

PowerShell mein admin se:
```
wsl --install -d kali-linux
```

restart ke baad Kali terminal mil jaata hai.

**limitation:**
- sirf terminal milta hai — GUI nahi (advanced setup se GUI bhi ho sakta hai lekin complex hai)
- tools ka subset hi kaam karta hai
- networking limitations hain

**use case:** quick commands, lightweight usage — full Kali nahi.

---

### Method 5 — Bare Metal Install — Dedicated Machine

Kali ko directly ek dedicated laptop ya PC pe install karo — koi aur OS nahi.

**perfect for:**
- jab dedicated hacking machine ho
- maximum performance chahiye
- advanced professionals ke liye

**beginners ke liye:** nahi — pehle VM se seekho, phir jab comfortable ho toh dedicated machine consider karo.

---

### Method 6 — Kali Linux on Android (NetHunter)

Offensive Security ka ek project hai — **Kali NetHunter** — jo rooted Android phones pe Kali run karne deta hai.

mobile ethical hacking ke liye — advanced use case. abhi yahan jaana zaroori nahi.

---

### Kali ke Flavors — Download Karte Waqt Kaun Sa Lein?

Kali download karo toh kai options milenge:

| Flavor | Kya Hai | Kiske Liye |
|---|---|---|
| **Kali Linux Installer** | Full install — hard disk pe | Bare metal ya VM |
| **Kali Linux Live** | USB se chalao bina install kiye | Live boot |
| **Kali Linux Virtual Machine** | Pre-built VM file (`.ova`) | VirtualBox/VMware ke liye — sabse easy |
| **Kali Linux WSL** | Windows Store se | WSL users ke liye |
| **Kali Linux NetHunter** | Android ke liye | Mobile hackers |

**beginners ke liye best choice:**

> **"Kali Linux Virtual Machine" — pre-built `.ova` file download karo — VirtualBox mein import karo — 10 minute mein ready.**

yahi hum next topic mein karenge.

---

### Desktop Environments — XFCE, GNOME, KDE?

Kali Linux download karte waqt ek aur choice hoti hai — **Desktop Environment:**

| DE | How It Looks | Resource Usage |
|---|---|---|
| **XFCE** (default) | Lightweight, fast, simple | Low — purane hardware pe bhi chalta hai |
| **GNOME** | Modern, polished | High — zyada RAM chahiye |
| **KDE Plasma** | Feature rich, customizable | Medium-High |

**Kali ka default = XFCE** — beginners ke liye yahi best hai. fast hai, light hai, kaam karta hai.

---

### ek line mein

> **Beginners ke liye: VM mein Kali. Pre-built `.ova` file download karo — VirtualBox mein import karo — ek ghante mein ready. Laptop safe, Kali full power mein.**

---

## 🎯 Task — Topic 5.2 — VirtualBox Download Karo

**task naam: "Kali ke liye ghar tayaar karo"**

abhi Kali install nahi karenge — pehle sirf VirtualBox ready karo.

**Step 1 — VirtualBox download karo:**
```
https://www.virtualbox.org/wiki/Downloads
```
apne OS ke hisaab se download karo — Windows, Mac, ya Linux.

**Step 2 — Install karo:**
- downloaded installer run karo
- "Next, Next, Install" — default settings theek hain
- install complete hone do

**Step 3 — VirtualBox open karo:**
pehli baar khulega — yeh screen dikhegi:
```
Oracle VirtualBox Manager
[New] [Settings] [Start]
```

koi VM nahi hai abhi — blank list hogi. normal hai.

**Step 4 — Note karo:**
Kali ki website pe jaao:
```
https://www.kali.org/get-kali/
```
"Virtual Machines" section dekho — `.ova` file ka size note karo. download time estimate karo apni speed se.

**next topic mein: actual Kali install karenge.**

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.2 COMPLETE — INSTALLATION METHODS
   ⬇️  Neeche hai Topic 5.3
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.3 — VirtualBox Pe Kali Install Karna — Step by Step

---

### ab asli kaam

theory ho gayi. ab Kali actually install karte hain.

yeh topic ek complete step-by-step guide hai. ek ek step follow karo — kuch skip mat karna.

---

### Jo Chahiye

- **VirtualBox** installed (topic 5.2 mein install kiya)
- **Kali Linux Pre-built VM** — `.ova` file
- **Minimum RAM:** 4GB (8GB recommended)
- **Disk Space:** 20-30GB free
- **Internet:** download ke liye

---

### Step 1 — Kali VM File Download Karo

browser mein jaao:
```
https://www.kali.org/get-kali/#kali-virtual-machines
```

"VirtualBox" option pe click karo — `.ova` file download hogi.

file size approximately **3-4 GB** hoti hai. internet speed ke hisaab se 15-60 minute lag sakte hain.

download ke baad — `.ova` file ready hai. kuch install nahi kiya abhi — sirf download hua.

---

### Step 2 — VirtualBox Mein Import Karo

VirtualBox open karo.

menu se: **File → Import Appliance**

```
File → Import Appliance → [.ova file select karo] → Next
```

settings page dikhega — yeh default values theek hain:

| Setting | Default Value | Recommendation |
|---|---|---|
| RAM | 2048 MB (2GB) | 4096 MB (4GB) rakho agar RAM available hai |
| CPU | 1 | 2 rakho agar CPU cores hain |
| Disk | 80 GB | as is |

**RAM adjust karo:** slider pe 4096 MB set karo agar possible hai.

phir: **Import** — 5-10 minute lagenge.

---

### Step 3 — Pehli Baar Start Karo

import complete hua — VM list mein "Kali Linux" dikhega.

**Start** button dabao.

ek nayi window khulegi — Kali boot hoga. pehli baar thoda time lagega — 1-2 minute.

login screen aayega.

---

### Step 4 — Login Karo

Kali ka default username aur password:

```
Username: kali
Password: kali
```

yeh dono type karo — Enter — Kali ka desktop khulega.

---

### Step 5 — Desktop Dekho

XFCE desktop dikhega — taskbar upar ya neeche hoga, application menu hoga.

**pehle kaam — Guest Additions install karo** (VirtualBox specific step):

terminal kholo (taskbar mein terminal icon ya right click → terminal)

```bash
sudo apt update
sudo apt install -y virtualbox-guest-x11
sudo reboot
```

**yeh teen commands ek ek karke samjho:**

**`sudo apt update`**

```
sudo        → "superuser do" — root ki permission se chalao yeh command
              (tumhara normal user account sensitive system changes nahi kar sakta —
               sudo woh permission temporarily deta hai)

apt         → Kali ka package manager — software install/remove/update karta hai
              (poora naam: Advanced Package Tool)

update      → repositories se nayi package list fetch karo
              matlab: internet pe check karo — koi naya software version aaya kya?
              (kuch install nahi hota — sirf list refresh hoti hai)
```

> yeh command pehle hamesha chalanki chahiye — warna outdated list se kaam hota hai.

---

**`sudo apt install -y virtualbox-guest-x11`**

```
sudo                    → root permission se chalao
apt                     → package manager
install                 → yeh software install karo
-y                      → "yes" automatically assume karo
                          (bina iske apt puchega "kya install karein? [Y/n]" — 
                           tumhe manually Y dabaana padega — '-y' woh step skip karta hai)
virtualbox-guest-x11    → package ka naam — yeh hai VirtualBox Guest Additions
                          jo Kali ko sahi size mein dikhata hai, clipboard share karta hai,
                          aur drag-drop enable karta hai
```

---

**`sudo reboot`**

```
sudo     → root permission
reboot   → system restart karo — Guest Additions install ke baad effect aane ke liye
```

reboot ke baad — Kali full screen mein chalega, clipboard share hoga, drag-drop kaam karega.

---

### Step 6 — Password Change Karo

default password "kali" jagah jagah pata hai — badal lo:

```bash
passwd
```

**`passwd` ka matlab:**

```
passwd   → "password" ka short form
           yeh command current user ka password change karta hai
           koi argument nahi chahiye — seedha chalao — interactive prompt aata hai
```

```
Current password: kali           ← purana password verify karega
New password: [apna naya password]
Retype new password: [dobara]    ← confirm karne ke liye
```

**strong password rakho** — numbers, symbols, uppercase — mix karo.

---

### Step 7 — Update Karo

naya system — pehla kaam update:

```bash
sudo apt update && sudo apt upgrade -y
```

**yeh ek line mein kai kaam ho rahe hain — poora breakdown:**

```
sudo          → root permission se chalao
apt           → package manager
update        → repositories se nayi list fetch karo (koi install nahi — sirf list)

&&            → "AND operator" — matlab:
                "pehli command SUCCESS ho — tab aur sirf tab doosri chalao"
                agar 'update' fail ho gaya — 'upgrade' nahi chalega
                yeh safety mechanism hai

sudo          → phir root permission
apt           → phir package manager
upgrade       → jo nayi versions update ne fetch ki thi — unhe actually install karo
                yahan actual download aur install hota hai
-y            → sab upgrade prompts pe automatically "yes" — manually nahi dabaana
```

> **`update` vs `upgrade` ka fark:**
> `update` = sirf list refresh karo — "kya available hai" check karo
> `upgrade` = actually install karo — jo available hai woh download aur update karo
> dono zaruri hain — ek ke bina doosra adhoora hai

yeh thoda time le sakta hai — pehli baar zyada updates hoti hain. chal jaane do.

---

### Step 8 — Snapshot Lo

sab kuch sahi chal raha hai — ab ek snapshot lo. fresh clean state ka.

VirtualBox mein:
```
Machine → Take Snapshot → naam: "Fresh Install - Clean"
```

ab agar kuch bhi galat ho — is snapshot pe wapas aa sakte ho.

---

### Common Problems aur Solutions

**Problem: VM start nahi ho raha — "VT-x is disabled"**

solution: BIOS mein jaao — Virtualization enable karo.
- restart karo, F2/Del/F10 dabao boot pe (manufacturer ke hisaab se alag)
- BIOS mein "Intel Virtualization Technology" ya "AMD-V" dhundho — Enable karo
- save karke exit karo

**Problem: Screen bahut chhoti hai**

solution: Guest Additions install karo (Step 5 mein bataya). phir View → Auto-resize Guest Display.

**Problem: Internet nahi chal raha VM mein**

VirtualBox mein VM settings → Network → Adapter 1:
- Attached to: **NAT** select karo — internet kaam karega

**Problem: Login ke baad kuch nahi dikhta / black screen**

solution: VM restart karo. agar phir bhi — VirtualBox → Display → Video Memory 128 MB karo.

---

### Kali VM Ready — Ab Se Yahi Tumhara Lab Hai

Kali installed hai. Updated hai. Snapshot hua hai.

ab se jab bhi koi topic sikhoge — is Kali VM mein karoge. yahi tumhara safe lab hai — kuch bhi try karo — host laptop safe rahega.

---

## 🎯 Task — Topic 5.3 — Kali Install Karo

**task naam: "apna hacking lab ready karo"**

**Step 1:** `https://www.kali.org/get-kali/#kali-virtual-machines` se `.ova` download karo.

**Step 2:** VirtualBox open karo → File → Import Appliance → `.ova` select karo → RAM 4096 MB set karo → Import.

**Step 3:** Start karo → `kali` / `kali` se login karo.

**Step 4:** terminal kholo, run karo:
```bash
sudo apt update
sudo apt install -y virtualbox-guest-x11
sudo reboot
```

**Step 5:** reboot ke baad:
```bash
passwd
```
password badlo.

**Step 6:**
```bash
sudo apt update && sudo apt upgrade -y
```
update complete hone do.

**Step 7:** VirtualBox → Machine → Take Snapshot → naam: "Clean Install"

**Verify karo:**
```bash
uname -a
```
Kali ka version aur kernel dikhega. Kali ready hai. 🎉

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.3 COMPLETE — KALI INSTALL READY
   ⬇️  Neeche hai Topic 5.4
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.4 — Kali Ka Desktop — Pehli Baar Seedha Dekho

---

### pehli baar khologe toh overwhelm hoga — normal hai

Kali ka desktop khula. ek bahut kuch dikh raha hai. taskbar, icons, menu — aur tum soch rahe ho "yeh sab kya hai?"

normal hai. har kisi ke saath aise hi hua.

ab hum ek ek cheez seedha samjhenge. koi panic nahi.

---

### XFCE Desktop — Kali Ka Default Interface

Kali mein XFCE desktop environment hota hai. yeh Windows ya Android jaisa nahi lagta — alag hai. lekin kuch minutes mein comfortable ho jaoge.

```
┌─────────────────────────────────────────────────────────┐
│  [Applications ▼]  [Places ▼]  [System ▼]          🔋🕐 │  ← Top Panel
├─────────────────────────────────────────────────────────┤
│                                                         │
│                                                         │
│              (Desktop Area)                             │
│                                                         │
│                                                         │
├─────────────────────────────────────────────────────────┤
│  [🖥️ Terminal] [🌐 Browser]  ...          [Workspaces]  │  ← Bottom Panel (ya top pe)
└─────────────────────────────────────────────────────────┘
```

---

### Top Panel — Kya Hai Kya?

**Applications menu:**
yahan sare installed programs hain — categories mein:

```
Applications
├── 01 - Information Gathering    ← network/target info tools
├── 02 - Vulnerability Analysis   ← vulnerability scanners
├── 03 - Web Application Analysis ← web hacking tools
├── 04 - Database Assessment      ← database tools
├── 05 - Password Attacks         ← password tools
├── 06 - Wireless Attacks         ← WiFi tools
├── 07 - Reverse Engineering      ← RE tools
├── 08 - Exploitation Tools       ← exploit tools
├── 09 - Sniffing & Spoofing      ← traffic tools
├── 10 - Post Exploitation        ← after getting in
├── 11 - Forensics                ← digital forensics
├── 12 - Reporting Tools          ← report banane ke liye
└── Usual Apps                    ← browser, file manager, etc.
```

yeh categories — ethical hacking ka workflow hai. pehle information gather karo, phir vulnerabilities dhundho, phir exploit karo. numbers order mein hain.

**Places menu:**
- Home, Desktop, Downloads — file system navigate karne ke liye

**System menu:**
- Settings, Log Out, Shut Down

---

### Terminal — Sabse Important Application

Kali mein terminal **sabse zyada use hone wali cheez** hai.

terminal kholne ke teen tarike:

1. **Keyboard shortcut:** `Ctrl + Alt + T`
2. **Taskbar pe terminal icon:** click karo
3. **Right click** desktop pe → Open Terminal

terminal khulne par yeh dikhega:

```
┌──(kali㉿kali)-[~]
└─$
```

yeh Kali ka prompt hai. breakdown:

```
┌──(kali㉿kali)-[~]
       │    │    │
       │    │    └── [~] = current location (~ = home directory)
       │    └────── kali = machine name (hostname)
       └─────────── kali = current username
└─$               = command type karne ki jagah
```

---

### File Manager — Thunar

Kali mein File Manager ka naam **Thunar** hai.

kholne ke liye: Places → Home Folder

ya terminal mein:
```bash
thunar
```

yahan files aur folders Windows Explorer jaisi dikhti hain. lekin hum mostly terminal se kaam karenge — GUI sirf reference ke liye.

---

### Text Editor — Mousepad

simple text files khol ke dekhne ke liye Kali mein **Mousepad** editor hai.

kholne ke liye: Applications → Accessories → Mousepad

ya terminal se:
```bash
mousepad filename.txt
```

---

### Web Browser — Firefox ESR

Kali mein default browser **Firefox ESR** aata hai.

ESR = Extended Support Release — stable version.

browser se kali.org, documentation, aur web-based tools access kar sakte ho.

---

### Workspaces — Kali Ki Super Power

XFCE mein ek feature hai — **Multiple Workspaces.**

socho multiple virtual desktops — ek pe terminal chal raha hai, ek pe browser, ek pe file manager — sab alag screens pe.

```
Workspace 1 → Terminal chala raha hai
Workspace 2 → Browser aur notes
Workspace 3 → Koi tool chal raha hai
```

switch karna: `Ctrl + F1`, `Ctrl + F2`, `Ctrl + F3` — ya taskbar mein workspace switcher.

professional log yeh use karte hain — work organized rehta hai.

---

### Right Click — Desktop Pe

desktop pe right click karo — menu aayega:

```
Open Terminal Here
Create Folder
Create Document
...
```

"Open Terminal Here" — bahut useful hai. jis folder mein ho — wahan se seedha terminal khulega.

---

### System Settings

Applications → Settings → Settings Manager — yahan sab kuch customize kar sakte ho:
- display resolution
- keyboard shortcuts
- mouse settings
- appearance / themes

---

### Kali Ka Wallpaper — Woh Dragon

Kali ka default wallpaper ek dragon hai — Kali Linux ka logo. XFCE aur GNOME mein alag alag design hote hain lekin dragon icon consistent hai.

---

### Shortcut Keys — Yaad Rakho

| Shortcut | Kaam |
|---|---|
| `Ctrl + Alt + T` | Terminal kholna |
| `Ctrl + F1` / `F2` / `F3` | Workspace switch |
| `Alt + F4` | Current window band karna |
| `Alt + Tab` | Windows ke beech switch |
| `Super` (Windows key) | Application launcher |
| `Ctrl + C` | Running command rokna |
| `Ctrl + L` | Terminal clear karna |

---

### ek line mein

> **Kali ka desktop alag lagta hai — lekin simple hai. Terminal sabse important jagah hai. Baki GUI sirf support ke liye hai.**

---

## 🧠 MCQ Set — Topic 5.4

---

**Q1.** Kali mein terminal kholne ka keyboard shortcut kya hai?

- A) `Ctrl + T`
- B) `Alt + T`
- C) `Ctrl + Alt + T`
- D) `Super + Enter`

✅ **Sahi Jawab: C**
> `Ctrl + Alt + T` — yeh shortcut yaad rakho. Kali pe sabse zyada use hone wala shortcut hai — terminal kholna. har kaam yahan se shuru hota hai.

---

**Q2.** Kali ke terminal prompt mein `[~]` ka matlab kya hai?

- A) root directory — `/` pe ho
- B) system directory — `/etc` pe ho
- C) temp directory — `/tmp` pe ho
- D) home directory — current user ka home folder

✅ **Sahi Jawab: D**
> `~` = tilde = home directory shortcut. `kali` user ke liye `~` matlab `/home/kali`. jab bhi `~` dekho — home folder pe ho.

---

**Q3.** Kali ke Applications menu mein categories numbered (01, 02, 03...) kyun hain?

- A) ethical hacking ka workflow represent karta hai — information gathering pehle, exploitation baad mein
- B) tools ka alphabetical order maintain karne ke liye — numbers sort karte hain
- C) Offensive Security ka internal tool numbering system hai — support ke liye
- D) numbers difficulty level batate hain — 01 easy, 12 hardest

✅ **Sahi Jawab: A**
> categories ka order = hacking workflow. 01 Information Gathering se shuru, phir Vulnerability Analysis, phir Exploitation — yeh actual penetration testing process hai. soch ke design kiya gaya hai.

---

**Q4.** XFCE mein "Workspaces" kya hote hain?

- A) alag alag user accounts — har workspace ek alag user ke liye
- B) multiple virtual desktops — alag alag windows alag alag screens pe organized
- C) VirtualBox ke andar alag environments — har workspace ek VM
- D) saved terminal sessions — band hone pe automatically restore hote hain

✅ **Sahi Jawab: B**
> workspaces = virtual desktops. workspace 1 pe terminal, workspace 2 pe browser — switch karo `Ctrl+F1/F2`. professional Kali users always multiple workspaces use karte hain.

---

**Q5.** Kali terminal prompt `┌──(kali㉿kali)-[~]` mein `㉿` ke dono taraf kya hai?

- A) left = machine name, right = username
- B) left = OS version, right = kernel version
- C) left = directory, right = user permissions
- D) left = username, right = hostname (machine name)

✅ **Sahi Jawab: D**
> format hai `username㉿hostname`. `kali㉿kali` matlab username=kali, hostname=kali. agar tum hostname change karo — right wala badlega.

---

**Q6.** Kali mein `$` prompt ka matlab kya hai?

 = normal user. `#` = root user. hamesha `$` dekhna chahiye normal kaam mein — `#` tab aye jab specifically root access karo `sudo su` se. yeh important hai — security ke liye.

---

**Q7.** Kali mein default File Manager kaun sa hai?

- A) Nautilus — GNOME ka file manager
- B) Dolphin — KDE ka file manager
- C) Thunar — XFCE ka file manager
- D) Nemo — Cinnamon ka file manager

✅ **Sahi Jawab: C**
> Thunar = XFCE ka file manager. Kali mein XFCE default hai — isliye Thunar. terminal se `thunar` command se bhi khul jaata hai.

---

**Q8.** `Ctrl + C` terminal mein kya karta hai?

- A) copy karta hai — clipboard pe
- B) currently running command ko interrupt/stop karta hai
- C) terminal window close karta hai
- D) cursor beginning of line pe le jaata hai

✅ **Sahi Jawab: B**
> `Ctrl + C` = SIGINT — running process ko stop karo. koi command chal rahi hai aur rokni hai — `Ctrl + C` dabao. copy ke liye terminal mein `Ctrl + Shift + C` use hota hai.

---

**Q9.** Kali mein default web browser kaunsa aata hai?

- A) Firefox ESR — Extended Support Release
- B) Chromium — Chrome ka open source version
- C) Tor Browser — anonymous browsing ke liye
- D) Epiphany — GNOME ka default browser

✅ **Sahi Jawab: A**
> Firefox ESR = stable, long-term supported Firefox version. Kali mein default. additional security tools ke saath configure kiya gaya hota hai.

---

**Q10.** Desktop pe right click → "Open Terminal Here" — yeh kyu useful hai?

- A) faster hota hai keyboard shortcut se — mouse click ek action hai
- B) us specific location (folder) pe seedha terminal khulta hai — `cd` karne ki zarurat nahi
- C) root terminal khulta hai — elevated permissions ke saath
- D) ek dedicated fullscreen terminal window milti hai — distraction-free

✅ **Sahi Jawab: B**
> "Open Terminal Here" = convenience feature. agar ek folder dekh raha hai file manager mein — right click → terminal khula wahin se. `cd /path/to/folder` manually type nahi karna padta.

---

**Q11.** Kali mein `Ctrl + L` terminal mein kya karta hai?

- A) logout karta hai current session se
- B) terminal ki history list dikhata hai
- C) terminal window lock karta hai — password maangega
- D) terminal screen clear karta hai — `clear` command jaisi

✅ **Sahi Jawab: D**
> `Ctrl + L` = clear screen. `clear` command type karne ki jagah shortcut. terminal cluttered lage — `Ctrl + L` — clean screen.

---

**Q12.** Kali ka XFCE desktop kyun choose kiya gaya default ke liye?

- A) XFCE lightweight hai — VM mein bhi smooth chalta hai, kam RAM use karta hai
- B) XFCE sabse modern aur attractive desktop hai Linux pe
- C) XFCE mein hacking tools ka better GUI integration hota hai doosron se
- D) Offensive Security ne XFCE khud develop kiya — isliye default rakha

✅ **Sahi Jawab: A**
> XFCE = low resource usage. Kali VM mein chalta hai — RAM share hoti hai host ke saath. XFCE VM mein bhi smooth. GNOME heavy hota — VM mein lagta. practical choice.

---

**Q13.** Kali Linux ka logo kya hai?

- A) shield aur sword — defense aur offense
- B) dragon — Kali Linux ka mascot
- C) skull — hacking community ka traditional symbol
- D) snake — Python language represent karta hai

✅ **Sahi Jawab: B**
> Kali Linux ka mascot ek dragon hai — aggressive, powerful. default wallpaper aur branding mein dragon icon consistent hai throughout.

---

**Q14.** Workspace switch karne ke liye shortcut kya hai?

- A) `Ctrl + Tab` — next workspace pe jaao
- B) `Alt + 1`, `Alt + 2` — workspace number
- C) `Super + Left`, `Super + Right` — previous/next workspace
- D) `Ctrl + F1`, `Ctrl + F2`, `Ctrl + F3` — workspace 1, 2, 3

✅ **Sahi Jawab: D**
> `Ctrl + F1` = workspace 1, `Ctrl + F2` = workspace 2, etc. XFCE default shortcut. customize bhi kar sakte ho Settings mein.

---

**Q15.** Kali ka desktop initially unfamiliar lage toh kya karna chahiye?

- A) GNOME install karo — Windows jaisi feel milegi
- B) Kali use karna chhoddo — Windows pe tools install karo
- C) kuch din regular use karo — XFCE quickly familiar ho jaata hai, panic nahi
- D) theme change karo — Windows 11 jaisi theme download karo Kali ke liye

✅ **Sahi Jawab: C**
> har naya environment unfamiliar lagta hai pehli baar. XFCE simple hai — kuch sessions ke baad comfortable ho jaate ho. panic nahi — explore karo. yeh sab hackers ke saath hua hai.

---

## 🎯 Task — Topic 5.4 — Kali Desktop Explore Karo

**task naam: "apne naye ghar ka tour"**

Kali VM kholo aur yeh karo:

**Step 1 — Teen tarike se terminal kholo:**
```
1. Ctrl + Alt + T
2. Taskbar icon click
3. Desktop pe right click → Open Terminal Here
```
teeno try karo — sabse comfortable wala note karo.

**Step 2 — Workspace explore karo:**
- `Ctrl + F2` dabao — workspace 2 pe jao
- kuch type karo
- `Ctrl + F1` — wapas workspace 1
- `Ctrl + F3` — workspace 3

**Step 3 — Applications menu dekho:**
- Applications click karo
- categories dekho (01 se 12 tak)
- kisi bhi tool pe hover karo — naam dekho
- abhi kuch open mat karo — sirf explore karo

**Step 4 — System info dekho:**
terminal mein:
```bash
uname -a
```
```bash
lsb_release -a
```
```bash
whoami
```
teeno ka output note karo — kya dikhta hai?

**Step 5 — Mousepad open karo:**
Applications → Accessories → Mousepad
ek chhota sa note likho: "Kali Ready — [aaj ki date]"
Save karo Desktop pe.

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.4 COMPLETE — KALI DESKTOP
   ⬇️  Neeche hai Topic 5.5
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.5 — Terminal Navigation — File System Mein Chalna

---

### file system ek sheher jaisi hai

socho ek sheher hai. sheher mein mohalle hain. mohalle mein galiyan hain. galiyan mein ghar hain.

tumhe kisi jagah jaana hai — pehle address pata hona chahiye. address ke bina — bhatakte rahoge.

**Linux ka file system bilkul aisa hi hai.**

```
/                          ← sheher ka center (root)
├── home/                  ← residential area
│   └── kali/              ← tumhara ghar
│       ├── Desktop/
│       ├── Downloads/
│       └── Documents/
├── etc/                   ← government offices (configs)
├── var/                   ← warehouses (logs, data)
├── bin/                   ← tools ki dukaan (commands)
└── tmp/                   ← temporary storage (time pe saaf)
```

ab yeh sheher mein chalna seekhte hain — terminal se.

---

### `pwd` — Main Abhi Kahaan Hun?

**Print Working Directory** — tumhari current location batata hai.

```bash
pwd
```

output:
```
/home/kali
```

iska matlab — tum abhi `/home/kali` folder mein ho. yahi tumhara "home" hai.

> **jab bhi khud se poochho "main kahaan hun?" — `pwd` type karo.**

---

### `ls` — Yahaan Kya Hai?

**List** — current folder ke andar kya hai yeh dikhata hai.

```bash
ls
```

output:
```
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```

**kuch useful variations:**

```bash
ls -l
```
detailed list — permissions, size, date sab dikhega:
```
drwxr-xr-x 2 kali kali 4096 Jan 15 10:30 Desktop
drwxr-xr-x 2 kali kali 4096 Jan 15 10:30 Documents
```

```bash
ls -la
```
hidden files bhi dikhao (`.` se shuru hone wali files):
```
drwxr-xr-x 2 kali kali 4096 Jan 15 10:30 .bashrc
drwxr-xr-x 2 kali kali 4096 Jan 15 10:30 Desktop
```

```bash
ls -lh
```
human-readable size — bytes ki jagah KB, MB dikhega:
```
-rw-r--r-- 1 kali kali 2.3K Jan 15 10:30 file.txt
```

**kisi aur folder ka content dekhna:**
```bash
ls /etc
```

---

### `cd` — Kisi Folder Mein Jao

**Change Directory** — location change karna.

```bash
cd Desktop
```

ab tum Desktop folder mein ho. `pwd` type karo confirm karne ke liye:
```
/home/kali/Desktop
```

**kuch important shortcuts:**

```bash
cd ~
```
seedha home directory pe wapas jao — chahe kahaan bhi ho.

```bash
cd ..
```
ek level upar jao (parent folder):
```
/home/kali/Desktop → cd .. → /home/kali
```

```bash
cd ../..
```
do level upar:
```
/home/kali/Desktop → cd ../.. → /home
```

```bash
cd /
```
root directory pe jao — sab se upar.

```bash
cd -
```
pichli location pe wapas jao — toggle karo do locations ke beech.

---

### Absolute vs Relative Path

yeh concept important hai.

**Absolute Path** — root se poora address:
```bash
cd /home/kali/Documents
```
chahe kahaan bhi ho — yeh kaam karega. `/` se shuru hota hai.

**Relative Path** — abhi jahan ho wahan se:
```bash
cd Documents
```
yeh sirf tab kaam karega jab tum `/home/kali` mein ho. `Documents` folder yahin pe hai.

> **analogy:** absolute = "India, Mumbai, Andheri, Station Road, Building 5" — koi bhi dhundh sakta hai. relative = "agle corner pe" — sirf tab kaam karta hai jab tum sahi jagah pe ho.

---

### `mkdir` — Naya Folder Banao

**Make Directory:**

```bash
mkdir mera_folder
```

ek naya folder ban gaya.

**nested folders ek baar mein:**
```bash
mkdir -p projects/kali/notes
```
`-p` = "parent directories bhi banao agar nahi hain."

---

### `rmdir` — Khali Folder Delete Karo

```bash
rmdir mera_folder
```

**sirf khali folders delete hote hain is command se.** agar andar kuch hai — error aayega.

---

### `rm` — Files Delete Karo

```bash
rm file.txt
```

**⚠️ warning:** Linux mein deleted files Recycle Bin mein nahi jaati. seedha gone.

**folder aur usका content delete karna:**
```bash
rm -r folder_naam
```
`-r` = recursive — folder ke andar sab kuch bhi delete.

**bina confirmation ke force delete:**
```bash
rm -rf folder_naam
```
`-f` = force. confirmation nahi maangega.

> **⚠️ `rm -rf` bahut powerful command hai. galat folder pe chala do — data permanently gone. double check karo pehle.**

---

### `cp` — Copy Karo

```bash
cp source.txt destination.txt
```

file copy ho gayi.

**folder copy karna:**
```bash
cp -r source_folder/ destination_folder/
```

---

### `mv` — Move Karo ya Rename Karo

**move:**
```bash
mv file.txt /home/kali/Documents/
```

**rename:**
```bash
mv purana_naam.txt naya_naam.txt
```

same command — agar destination alag folder hai toh move, agar same folder mein alag naam hai toh rename.

---

### `touch` — Khali File Banao

```bash
touch naya_file.txt
```

ek khali file ban gayi. koi content nahi — sirf file exist karti hai. aage text editor se fill karenge.

---

### `tree` — Poora Structure Dekho

```bash
tree
```

current folder ka poora structure — visual tree mein:
```
.
├── Desktop
│   └── notes.txt
├── Documents
│   ├── project1
│   │   └── readme.md
│   └── project2
└── Downloads
```

agar `tree` installed nahi hai:
```bash
sudo apt install tree
```

---

### Tab Completion — Hacker Ki Speed Trick

yeh ek aisi cheez hai jo beginners skip karte hain aur bahut time waste karte hain:

**Tab button dabao** — terminal automatically complete kar dega.

example:
```bash
cd Doc[TAB]
```
→ terminal khud likhega:
```bash
cd Documents/
```

agar multiple options hain — Tab do baar dabao — sab options list ho jaayenge.

> **yeh ek habit hai jo tumhara speed 10x kar deti hai. hamesha Tab use karo.**

---

### Up Arrow — Purani Command Wapas

terminal mein Up Arrow dabao — pichli command wapas aayegi.

baar baar dabate raho — history mein jaate raho.

---

### ek line mein

> **`pwd` = kahaan hun. `ls` = kya hai. `cd` = jao. `mkdir` = banao. `rm` = hatao. `cp` = copy karo. `mv` = move/rename. Tab = speed. Up Arrow = history.**

---

## 🧠 MCQ Set — Topic 5.5

---

**Q1.** `pwd` command ka kya kaam hai?

- A) present/current working directory dikhata hai — abhi kahaan ho
- B) previous working directory dikhata hai — pichli location
- C) parent working directory dikhata hai — ek level upar
- D) program working directory — running programs ki location

✅ **Sahi Jawab: A**
> pwd = Print Working Directory. current location dikhata hai. jab bhi confusion ho "main kahaan hun?" — `pwd` type karo.

---

**Q2.** `ls -la` mein `-la` ka matlab kya hai?

- A) long format aur alphabetical sort — size ke bajay naam se sort
- B) long format (-l) aur all files (-a) — hidden files bhi include karo
- C) list aur archive — compressed files bhi dikhao
- D) long format aur last modified — latest files pehle

✅ **Sahi Jawab: B**
> `-l` = long format (detailed). `-a` = all (hidden files bhi — jo `.` se shuru hoti hain). dono milke `ls -la` ya `ls -al` — detailed listing with hidden files.

---

**Q3.** `cd ..` kya karta hai?

- A) computer ko restart karta hai — dot dot = shutdown signal
- B) root directory pe jaata hai — `..` matlab `root`
- C) pichli directory pe jaata hai — `cd -` jaisa
- D) ek level upar — parent directory pe jaata hai

✅ **Sahi Jawab: D**
> `..` = parent directory. `/home/kali/Desktop` mein ho — `cd ..` → `/home/kali`. `cd ../..` → `/home`.

---

**Q4.** Absolute path aur Relative path mein kya fark hai?

- A) absolute `/` se shuru hota hai — kahan se bhi kaam karta hai. relative = current location se — context ke saath kaam karta hai
- B) absolute = fast, relative = slow — performance difference
- C) absolute = files ke liye, relative = folders ke liye
- D) koi fark nahi — dono same result dete hain

✅ **Sahi Jawab: A**
> absolute = `/home/kali/Documents` — root se poora path — kahan se bhi reliable. relative = `Documents` — sirf tab jab `/home/kali` mein ho. dono use hote hain — context ke hisaab se.

---

**Q5.** `mkdir -p a/b/c` kya karta hai?

- A) sirf `c` folder banata hai — `a` aur `b` pehle se hone chahiye
- B) `a` folder banata hai phir error deta hai — ek baar mein ek hi folder ban sakta hai
- C) `a/b/c` — nested folders ek baar mein — parent folders bhi banata hai agar nahi hain
- D) existing folders delete karke nayi empty structure banata hai

✅ **Sahi Jawab: C**
> `-p` = parents. `mkdir -p a/b/c` — `a` banao, phir `a/b`, phir `a/b/c`. ek command se puri nested structure. bina `-p` ke error aata agar parent nahi hain.

---

**Q6.** Linux mein `rm` se delete ki gayi file kahan jaati hai?

- A) Trash/Recycle Bin mein — wahaan se recover ho sakti hai
- B) `/tmp` folder mein — automatically 24 ghante baad delete
- C) `/lost+found` mein — system recovery ke liye rakha jaata hai
- D) permanently gone — koi Recycle Bin nahi Linux mein by default

✅ **Sahi Jawab: D**
> Linux mein `rm` = permanent delete. Recycle Bin nahi. `rm -rf` toh aur bhi dangerous. hamesha pehle sochlo — file real mein delete karni hai? undo nahi hoga.

---

**Q7.** `mv file.txt /home/kali/Documents/` kya karta hai?

- A) file ko Documents mein copy karta hai — original bhi rehti hai
- B) file ko Documents mein move karta hai — original delete ho jaati hai
- C) file ka naam badal kar `Documents` rakh deta hai
- D) Documents folder ko file.txt ke saath zip karta hai

✅ **Sahi Jawab: B**
> `mv` = move. file current location se hata ke destination pe chali jaati hai. agar destination alag folder hai = move. agar same folder mein = rename. copy nahi hoti.

---

**Q8.** Tab completion kyun use karni chahiye?

- A) speed aur accuracy — terminal khud complete karta hai — typos nahi honge — faster work
- B) security ke liye — Tab se commands safe hoti hain, manually type karne mein risk
- C) sirf long commands ke liye — short commands mein Tab kaam nahi karta
- D) Tab sirf Kali Linux mein kaam karta hai — doosre terminals mein nahi

✅ **Sahi Jawab: A**
> Tab = sabse underrated feature. auto-complete karta hai — naam galat nahi hoga. `cd Doc[Tab]` → `cd Documents/`. speed 10x. hamesha use karo.

---

**Q9.** `ls -lh` mein `-h` ka matlab kya hai?

- A) hidden files dikhao — `.` se shuru wali files
- B) help — `ls` ka documentation dikhao
- C) human-readable — size bytes ki jagah KB, MB, GB mein dikhao
- D) hard links count dikhao — inode information ke saath

✅ **Sahi Jawab: C**
> `-h` = human-readable. `ls -l` mein size bytes mein hoti hai — `4096`. `-h` ke saath `4.0K`. clearer hota hai — especially badi files ke liye.

---

**Q10.** `touch newfile.txt` kya karta hai?

- A) file kholta hai editing ke liye — nano jaisa
- B) file ko temporarily lock karta hai — doosra user access nahi kar sakta
- C) file ko read-only banata hai — permissions change karta hai
- D) file ka timestamp update karta hai — agar exist karti hai. nahi karti toh khali file banata hai

✅ **Sahi Jawab: D**
> `touch` ke do kaam: 1) existing file ka timestamp update. 2) nahi hai toh khali file create. hackers often `touch` se placeholder files banate hain ya scripts mein timestamps set karte hain.

---

**Q11.** `cd -` kya karta hai?

- A) pichli directory pe jaata hai — do locations ke beech toggle karo
- B) home directory pe jaata hai — `cd ~` jaisa
- C) root directory pe jaata hai — `-` matlab beginning
- D) ek level upar jaata hai — `cd ..` jaisa

✅ **Sahi Jawab: A**
> `cd -` = toggle. `/home/kali` pe tha → gaya `/tmp` pe → `cd -` → wapas `/home/kali`. aur `cd -` → wapas `/tmp`. do locations ke beech fast switch.

---

**Q12.** `rm -rf /` command ke baare mein sach kya hai?

- A) root folder ko refresh karta hai — safe command hai
- B) root folder ka contents list karta hai — delete nahi
- C) poora root filesystem delete kar deta hai — system unbootable ho jaata hai — never run karo
- D) sirf temp files delete karta hai — system safe rehta hai

✅ **Sahi Jawab: C**
> `rm -rf /` = sabse dangerous command Linux mein. poori root filesystem delete. system dead. modern Linux mein protection hai is command se — lekin fir bhi kabhi run mat karna. isliye pehle path check karo.

---

**Q13.** `tree` command kya dikhata hai?

- A) installed packages ki dependency tree — kaunsa package kise depend karta hai
- B) current directory ka visual folder/file structure — tree format mein
- C) system process tree — parent aur child processes
- D) network topology — connected devices ka map

✅ **Sahi Jawab: B**
> `tree` = visual directory structure. branches mein files aur folders dikhata hai. quick overview ke liye excellent. agar installed nahi: `sudo apt install tree`.

---

**Q14.** `/etc` folder mein generally kya hota hai?

- A) executable programs — jo directly terminal se run karte hain
- B) user files — personal documents, downloads
- C) temporary files — reboot pe delete hote hain
- D) system configuration files — network, users, software settings

✅ **Sahi Jawab: D**
> `/etc` = configuration. network settings, user database, software configs — sab `/etc` mein. hackers ke liye important folder — misconfigured files vulnerabilities hote hain. chapter 4 mein bhi briefly cover kiya tha.

---

**Q15.** Up Arrow terminal mein kya karta hai?

- A) cursor line ke upar le jaata hai — multi-line text navigate karne ke liye
- B) terminal window minimize karta hai
- C) previous command history mein jaata hai — pichla command wapas laata hai
- D) font size increase karta hai — zoom in

✅ **Sahi Jawab: C**
> Up Arrow = command history. pichli command chahiye — Up Arrow. baar baar Up Arrow — aur peeche jaao history mein. Down Arrow = aage. `history` command se poori list dekh sakte ho.

---

## 🎯 Task — Topic 5.5 — File System Explore Karo

**task naam: "Linux ka sheher ghoomna"**

Kali terminal mein yeh karo — ek ke baad ek:

```bash
# 1. kahaan ho?
pwd

# 2. kya hai yahan?
ls -la

# 3. root dekho
ls /

# 4. etc mein jaao
cd /etc
ls

# 5. wapas home
cd ~
pwd

# 6. naya folder banao
mkdir hacking_notes
cd hacking_notes
pwd

# 7. khali file banao
touch day1.txt
ls

# 8. ek aur folder
mkdir practice
ls -l

# 9. folder remove karo (pehle khali karo)
rmdir practice

# 10. tree se structure dekho
cd ~
tree
```

**observe karo:**
- `ls /` ne kitni folders dikhayi?
- `/etc` mein kitni files hain — scroll karo
- `tree` ne structure kaise dikhaya?

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.5 COMPLETE — TERMINAL NAVIGATION
   ⬇️  Neeche hai Topic 5.6
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.6 — Files Dekhna aur Edit Karna

---

### file ka content terminal se kaise dekhen?

ab tak folders mein chalna seekha. ab **files ke andar dekhna** seekhenge.

hacking mein yeh bahut zaroori hai — log files padhna, config files dekhna, output files analyze karna — sab terminal se.

---

### `cat` — File Ka Content Print Karo

**Concatenate** — file ka poora content terminal mein print karta hai.

```bash
cat file.txt
```

output seedha terminal pe dikhayi deta hai.

**do files ek saath dekhna:**
```bash
cat file1.txt file2.txt
```

dono ka content ek ke baad ek dikhega.

**use case:** chhoti files ke liye perfect. badi files mein — sab ek saath aa jaata hai — scroll karna mushkil hoga. badi files ke liye `less` use karo.

---

### `less` — Ek Baar Mein Thoda Thoda Dekho

badi file hai? `less` use karo — ek page ek baar:

```bash
less bigfile.txt
```

controls:
- **Space** = ek page neeche
- **b** = ek page upar
- **q** = quit — wapas terminal pe
- **/** = search karo (`/keyword` type karo)
- **n** = next search result
- **G** = file ke end pe jao
- **g** = file ke start pe jao

> **`less` powerful hai — log files padhne ke liye bahut use hota hai.**

---

### `head` — Pehli Kuch Lines Dekho

```bash
head file.txt
```
default mein pehli **10 lines** dikhata hai.

**lines specify karo:**
```bash
head -n 20 file.txt
```
pehli 20 lines.

**use case:** badi file ka beginning dekhna chahte ho — poori padhne ki zarurat nahi.

---

### `tail` — Aakhri Kuch Lines Dekho

```bash
tail file.txt
```
default mein aakhri **10 lines.**

```bash
tail -n 50 file.txt
```
aakhri 50 lines.

**`-f` flag — real time mein dekho:**
```bash
tail -f /var/log/syslog
```
file mein nayi lines aati jaayengi — live update. log monitoring ke liye perfect. `Ctrl + C` se band karo.

---

### `wc` — Count Karo

**Word Count:**

```bash
wc file.txt
```

output:
```
  42  156  980 file.txt
```
matlab: **42 lines, 156 words, 980 bytes.**

**sirf lines count karo:**
```bash
wc -l file.txt
```

**sirf words:**
```bash
wc -w file.txt
```

---

### `file` — File Ka Type Pata Karo

```bash
file document.txt
```
output:
```
document.txt: ASCII text
```

kisi unknown file pe:
```bash
file mystery_file
```
output:
```
mystery_file: ELF 64-bit LSB executable, x86-64
```
matlab — yeh ek compiled Linux program hai, text nahi.

> **hackers ke liye useful — unknown files examine karne ke liye. extension pe mat jao — `file` se verify karo.**

---

### `nano` — Simple Text Editor

`nano` ek terminal-based text editor hai — seedha terminal mein file edit kar sakte ho.

```bash
nano file.txt
```

file khulegi. type karo. bottom mein shortcuts dikhenge:

```
^G = Help    ^O = Save    ^X = Exit
^K = Cut     ^U = Paste   ^W = Search
```

`^` = Ctrl.

**save karna:** `Ctrl + O` → Enter
**exit karna:** `Ctrl + X`

**naya file banana aur seedha likhna:**
```bash
nano naya.txt
```
file exist nahi karti — nano banayega. likho. save. exit.

---

### `vim` — Advanced Editor (Brief Introduction)

`vim` ek bahut powerful editor hai — lekin beginners ke liye steep learning curve hai.

abhi sirf itna jaano — agar accidentally vim khul jaye:

**vim se kaise niklen:**
```
Esc dabao → phir :q! type karo → Enter
```

`!q` = force quit. yeh sabko pata hona chahiye kyunki vim se nahi nikal paana ek common beginner problem hai.

nano abhi ke liye better hai — jab comfortable hoge tab vim seekhna.

---

### `grep` — File Mein Search Karo

**Global Regular Expression Print** — file mein specific text dhundho:

```bash
grep "password" file.txt
```

output: wo lines dikhega jisme "password" word hai.

**case-insensitive search:**
```bash
grep -i "password" file.txt
```

**line number bhi dikhao:**
```bash
grep -n "error" logfile.txt
```

**poori directory mein search karo:**
```bash
grep -r "admin" /etc/
```

> **`grep` ethical hacking mein bahut use hota hai — files mein sensitive data dhundna, log analysis, config examine karna.**

---

### `echo` — Text Print Karo

```bash
echo "Hello Kali"
```
output:
```
Hello Kali
```

**file mein likhna:**
```bash
echo "mera note" > notes.txt
```
`>` = output ko file mein daalo (existing content replace hoga)

```bash
echo "ek aur line" >> notes.txt
```
`>>` = append karo — existing content ke baad add hoga.

---

### `diff` — Do Files Mein Fark Dekho

```bash
diff file1.txt file2.txt
```

dono files compare karega — jo alag hai woh dikhayega:

```
< ye line sirf file1 mein hai
> ye line sirf file2 mein hai
```

---

### ek line mein

> **`cat` = chhoti file dekho. `less` = badi file scroll karo. `head`/`tail` = shuru/end dekho. `nano` = edit karo. `grep` = search karo. `file` = type pata karo.**

---

## 🧠 MCQ Set — Topic 5.6

---

**Q1.** badi file ka content padhna hai — sab ek baar mein nahi — kaunsa command?

- A) `less` — ek page ek baar, scroll, search support
- B) `cat` — poori file ek saath
- C) `more` — old version hai, `less` se better
- D) `read` — line by line automatically padhta hai

✅ **Sahi Jawab: A**
> `less` = badi files ke liye. space se page karo, `/` se search karo, `q` se exit. `cat` badi file pe sab ek baar dump kar deta hai — scrolling mushkil.

---

**Q2.** `tail -f logfile.txt` kya karta hai?

- A) file ke tail (end) se shuru karke poori file padhta hai backwards
- B) file ko background mein run karta hai — foreground mein kuch aur karo
- C) file ko real-time mein monitor karta hai — nayi lines automatically dikhti hain
- D) file ki last modified time dikhata hai

✅ **Sahi Jawab: C**
> `-f` = follow. file mein nayi content add hoti jaaye — terminal mein live dikhega. server logs monitor karne ke liye classic command. `Ctrl + C` se band karo.

---

**Q3.** `wc -l file.txt` kya return karta hai?

- A) file mein words ki count
- B) file ka size bytes mein
- C) file mein characters ki count
- D) file mein lines ki count

✅ **Sahi Jawab: D**
> `-l` = lines. `wc -w` = words. `wc -c` = characters/bytes. `wc` akela teenon batata hai ek saath.

---

**Q4.** `file` command kyun use karte hain?

- A) file ki actual type determine karne ke liye — extension pe nahi, actual content analyze karke
- B) file create karne ke liye — `touch` se better hai
- C) file ko open karne ke liye — default application se
- D) file permissions check karne ke liye

✅ **Sahi Jawab: A**
> `file` command file ka actual type batata hai — extension nahi, content analyze karke. `.txt` extension wali file actually executable ho sakti hai. `file` pe trust karo, extension pe nahi.

---

**Q5.** `nano` mein save kaise karte hain?

- A) `Ctrl + S`
- B) `Ctrl + W`
- C) `Ctrl + O` phir Enter
- D) `:w` type karo phir Enter

✅ **Sahi Jawab: C**
> nano mein `Ctrl + O` = Write Out = save. phir Enter confirm karo. `Ctrl + X` = exit. `:w` vim mein hota hai — nano mein nahi.

---

**Q6.** vim se force quit kaise karein?

- A) `Ctrl + C` aur phir `q`
- B) `Alt + F4` window close karo
- C) `Esc` dabao → `:q!` type karo → Enter
- D) `Ctrl + Z` aur phir `kill %1`

✅ **Sahi Jawab: C**
> `Esc` pehle (insert mode se bahar aao) → `:q!` (colon, q, exclamation) → Enter. `!` = force — changes save kiye bina exit. yeh sabko pata hona chahiye kyunki vim accidentally khul sakta hai.

---

**Q7.** `grep -i "error" logfile.txt` mein `-i` kya karta hai?

- A) inverse search — "error" ke BINA wali lines dikhao
- B) case-insensitive — "Error", "ERROR", "error" sab match karega
- C) interactive mode — ek ek result confirm karo
- D) include hidden — hidden sections bhi search karo

✅ **Sahi Jawab: B**
> `-i` = ignore case. bina `-i` ke "Error" match nahi hoga agar tumne "error" search kiya. `-i` ke saath — capital, small — sab match.

---

**Q8.** `echo "hello" > file.txt` aur `echo "world" >> file.txt` ke baad file mein kya hoga?

- A) sirf "world" — `>` replace karta hai, `>>` bhi replace karta hai
- B) sirf "hello" — `>>` kaam nahi karta agar pehle `>` use hua
- C) do alag files — ek mein "hello" ek mein "world"
- D) "hello" pehli line pe, "world" doosri line pe — `>>` append karta hai

✅ **Sahi Jawab: D**
> `>` = overwrite. `>>` = append (add at end). pehle `>` se file bani "hello" ke saath. phir `>>` se "world" add hua. dono lines rahenge.

---

**Q9.** `head -n 5 file.txt` kya dikhata hai?

- A) file ki pehli 5 lines
- B) file ki 5 se 10 wali lines
- C) file ki aakhri 5 lines
- D) file ke pehle 5 words

✅ **Sahi Jawab: A**
> `head` = file ka beginning. `-n 5` = 5 lines. `head` without `-n` = pehli 10 lines (default). `tail` = file ka end.

---

**Q10.** `grep -n "admin" /etc/passwd` mein `-n` kya add karta hai?

- A) network search — sirf network-related files mein
- B) line number — har result ke saath us line ka number dikhata hai
- C) null-separated output — scripts ke liye
- D) numeric only — sirf numbers wali lines search karo

✅ **Sahi Jawab: B**
> `-n` = line numbers. output mein `15:admin_user:x:1000:...` aayega — 15 line number hai. debugging aur analysis mein bahut useful — exact location pata chalta hai.

---

**Q11.** `cat file1.txt file2.txt > combined.txt` kya karta hai?

- A) file1 aur file2 delete karke combined.txt banata hai
- B) dono files compare karta hai — differences combined.txt mein save hote hain
- C) file1 ya file2 — jo pehle mile — usse combined.txt mein copy karta hai
- D) file1 aur file2 ka content join karke combined.txt mein save karta hai

✅ **Sahi Jawab: D**
> `cat` = concatenate. do files ka content ek ke baad ek print hota hai. `>` se combined.txt mein redirect ho jaata hai. "cat" naam isliye — multiple files concatenate karta hai.

---

**Q12.** `less` mein `/keyword` type karne ke baad kya hota hai?

- A) file mein "keyword" text insert ho jaata hai current position pe
- B) file close ho jaata hai aur search results alag window mein
- C) file mein "keyword" dhundha jaata hai — highlighted milta hai — `n` se next result
- D) sirf "keyword" wali lines reh jaati hain — baaki filter ho jaati hain

✅ **Sahi Jawab: C**
> `less` mein `/` search mode start karta hai. keyword type karo + Enter → pehla match highlight hoga. `n` = next match. `N` = previous match. `q` = exit.

---

**Q13.** `diff file1.txt file2.txt` output mein `<` aur `>` ka matlab?

- A) `<` = file2 mein hai, `>` = file1 mein hai
- B) `<` = file1 mein sirf yeh line hai, `>` = file2 mein sirf yeh line hai
- C) `<` = deleted line, `>` = added line — git diff jaisa
- D) `<` = common line, `>` = different line

✅ **Sahi Jawab: B**
> `<` = line sirf file1 mein. `>` = line sirf file2 mein. jahan dono same hain — kuch nahi dikhega. config files compare karne ke liye useful.

---

**Q14.** kisi unknown file ka type pata karna ho bina extension ke — best command?

- A) `file unknown_file` — actual file type analyze karke batata hai
- B) `cat unknown_file` — content dekhke guess karo
- C) `ls -l unknown_file` — permissions se type pata chalta hai
- D) `nano unknown_file` — editor mein dekho kya hai

✅ **Sahi Jawab: A**
> `file` command = file type detective. extension ignore karta hai — actual content (magic bytes) analyze karta hai. ELF executable? JPEG? PDF? sab bata deta hai.

---

**Q15.** `grep -r "password" /etc/` kya karta hai?

- A) `/etc/password` file create karta hai
- B) `/etc` directory aur uske sare sub-directories mein "password" text dhundta hai
- C) `/etc` folder delete karta hai agar password match kare
- D) root password change karta hai `/etc` mein

✅ **Sahi Jawab: B**
> `-r` = recursive. sirf ek file nahi — poori directory aur subdirectories mein search. `/etc` mein configuration files hain — `grep -r "password"` se koi plain-text password chhupa hua hai — dhundh sakte ho.

---

## 🎯 Task — Topic 5.6 — Files Ke Saath Kaam Karo

**task naam: "apna pehla notes system banao"**

```bash
# 1. notes folder banao
cd ~
mkdir my_notes
cd my_notes

# 2. nano se file likho
nano kali_commands.txt
```

nano mein yeh likho:
```
Kali Linux Commands
===================
pwd - current directory
ls - list files
cd - change directory
mkdir - make directory
cat - read file
nano - edit file
```
Save karo (Ctrl+O → Enter) → Exit karo (Ctrl+X)

```bash
# 3. verify karo
cat kali_commands.txt

# 4. line count karo
wc -l kali_commands.txt

# 5. grep use karo
grep "directory" kali_commands.txt

# 6. head dekho
head -n 3 kali_commands.txt

# 7. echo se line add karo
echo "grep - search in files" >> kali_commands.txt

# 8. file ki type check karo
file kali_commands.txt

# 9. verify addition
tail -n 3 kali_commands.txt
```

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.6 COMPLETE — FILES DEKHNA AUR EDIT KARNA
   ⬇️  Neeche hai Topic 5.7
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.7 — Users aur Permissions — Kaun Kya Kar Sakta Hai

---

### real world se analogy

socho ek company hai — Offensive Security Ltd.

company mein teen log hain:
- **CEO** = sab kuch kar sakta hai — koi restriction nahi
- **Employee** = sirf apna kaam kar sakta hai — doosron ki files nahi dekh sakta
- **Guest** = sirf lobby mein baith sakta hai — kuch access nahi

Linux mein bilkul yahi concept hai — **Users aur Permissions.**

> **Linux ek multi-user system hai — ek hi machine pe kai log ho sakte hain — aur har kisi ke liye alag access rights hote hain.**

---

### Users Ka System

**Root User = CEO**

Linux ka sabse powerful user. `root` naam se jaana jaata hai.

```
username: root
symbol: #
location: /root (home folder)
```

root sab kuch kar sakta hai — koi file delete kar sakta hai, koi bhi command chala sakta hai, system ko tod sakta hai.

**isliye root se hamesha kaam mat karo** — galti se bhi kuch delete ho sakta hai — system dead.

**Normal User = Employee**

```
username: kali (ya koi bhi naam)
symbol: $
location: /home/kali
```

apne files ke saath kaam kar sakta hai. system files touch nahi kar sakta without permission.

**Groups = Departments**

users ko groups mein organize kiya jaata hai. ek user multiple groups mein ho sakta hai. ek group ke sab users same permissions share karte hain.

---

### `whoami` — Main Kaun Hun?

```bash
whoami
```

output:
```
kali
```

current user kaun hai — seedha batata hai. simple but useful.

---

### `id` — Poori Identity

```bash
id
```

output:
```
uid=1000(kali) gid=1000(kali) groups=1000(kali),4(adm),24(cdrom),27(sudo)
```

matlab:
- `uid=1000` = user ID (root ka 0 hota hai)
- `gid=1000` = primary group ID
- `groups=...` = sare groups jisme ye user hai — `sudo` group mein hona important hai

---

### `sudo` — Temporary Root Powers

`sudo` = **Super User Do.**

ek normal user root ka kaam karna chahta hai — full root ban jaane ki zarurat nahi — sirf us command ke liye root powers lo:

```bash
sudo apt update
```

password maangega (tumhara user password) — phir command root ki tarah chalegi.

**`sudo su` — Poori Root Shell:**
```bash
sudo su
```
ab seedha root ban gaye — prompt mein `#` dikhega. ab tab tak root rahoge jab tak `exit` nahi karo.

> **habit: `sudo su` se root mat bano sirf ek command ke liye. seedha `sudo command` use karo — safer practice hai.**

---

### `su` — User Switch Karo

```bash
su username
```

ek user se doosre user mein switch karo. password maangega us user ka.

```bash
su root
```
root user mein switch karo.

---

### `who` aur `w` — Kaun Kaun Login Hai?

```bash
who
```

abhi kaun kaun logged in hai system pe — dikhata hai.

```bash
w
```

zyada detail — kaun, kab, kahan se, kya kar raha hai.

---

### Linux File Permissions — Asli Cheez

yeh concept ethical hacking mein bahut important hai — **misconfigurations = vulnerabilities.**

har file aur folder ke saath teen types ke permissions hote hain, teen types ke users ke liye:

**Teen Types Ke Users:**
- **Owner (u)** = file banane wala user
- **Group (g)** = file ka group
- **Others (o)** = baaki sab

**Teen Types Ke Permissions:**
- **r** = read (padhna)
- **w** = write (likhna/change karna)
- **x** = execute (run karna — programs/scripts ke liye)

---

### `ls -l` Se Permissions Padhna

```bash
ls -l
```

output:
```
-rwxr-xr-- 1 kali kali 1234 Jan 15 notes.txt
```

pehle 10 characters decode karo:

```
- rwx r-x r--
│  │   │   │
│  │   │   └── Others: r-- = sirf read
│  │   └────── Group:  r-x = read aur execute
│  └────────── Owner:  rwx = sab kuch — read, write, execute
└───────────── File type: - = regular file, d = directory
```

---

### Permissions Ko Numbers Mein Samjho

har permission ka ek number value hai:

| Permission | Symbol | Value |
|---|---|---|
| Read | r | 4 |
| Write | w | 2 |
| Execute | x | 1 |
| No Permission | - | 0 |

teen permissions milake ek digit banata hai:
- `rwx` = 4+2+1 = **7**
- `rw-` = 4+2+0 = **6**
- `r-x` = 4+0+1 = **5**
- `r--` = 4+0+0 = **4**
- `---` = 0+0+0 = **0**

complete permission teen digits mein:
- `rwxr-xr--` = **754**
- `rw-rw-r--` = **664**
- `rwxrwxrwx` = **777** (sab ke liye sab kuch — dangerous!)

---

### `chmod` — Permissions Change Karo

**Numeric mode:**
```bash
chmod 755 script.sh
```
matlab: owner = rwx (7), group = r-x (5), others = r-x (5)

**Symbolic mode:**
```bash
chmod u+x script.sh
```
`u` = user/owner, `+` = add karo, `x` = execute permission

```bash
chmod o-r file.txt
```
others se read permission hata do.

```bash
chmod a+r file.txt
```
`a` = all (owner, group, others) — sab ko read permission do.

---

### `chown` — File Ka Owner Badlo

```bash
sudo chown newuser file.txt
```

```bash
sudo chown newuser:newgroup file.txt
```

folder aur saari files ka owner change karo:
```bash
sudo chown -R newuser /folder/
```

---

### Common Permission Scenarios

**Script file run karna hai:**
```bash
chmod +x myscript.sh
./myscript.sh
```
pehle execute permission do — phir run karo.

**Private file — sirf tumhare liye:**
```bash
chmod 600 private.txt
```
`rw-------` = sirf owner read/write, baaki kuch nahi.

**Web server file:**
```bash
chmod 644 index.html
```
`rw-r--r--` = owner edit kar sakta hai, baaki sirf padh sakte hain.

**Dangerous — kabhi mat karo production mein:**
```bash
chmod 777 file.txt
```
`rwxrwxrwx` = sab ke liye sab kuch — major security risk.

---

### `/etc/passwd` aur `/etc/shadow` — User Database

Linux mein users ki information do files mein hoti hai:

**`/etc/passwd`** — basic user info (readable by all):
```bash
cat /etc/passwd
```
format:
```
kali:x:1000:1000:Kali,,,:/home/kali:/bin/bash
│    │ │    │    │        │           └── shell
│    │ │    │    │        └────────────── home directory
│    │ │    │    └─────────────────────── comment/full name
│    │ │    └──────────────────────────── GID
│    │ └───────────────────────────────── UID
│    └───────────────────────────────────  'x' = password in shadow
└────────────────────────────────────────  username
```

**`/etc/shadow`** — actual passwords (encrypted, root only):
```bash
sudo cat /etc/shadow
```
passwords hashed hote hain — plaintext nahi.

---

### ek line mein

> **Linux mein har file ka owner hota hai, group hota hai, permissions hoti hain. `chmod` se permissions change karo. `sudo` se specific kaam root ki tarah karo. `755`, `644`, `600` — yeh yaad rakho.**

---

## 🧠 MCQ Set — Topic 5.7

---

**Q1.** Linux mein root user ka UID (User ID) kya hota hai?

- A) 1 — pehla user hona chahiye
- B) 100 — system users is range mein hote hain
- C) 0 — root ka UID hamesha 0 hota hai
- D) 999 — highest privilege level

✅ **Sahi Jawab: C**
> root ka UID = 0. yeh fixed hai. `id root` se verify karo. normal users 1000+ se shuru hote hain Debian/Ubuntu/Kali pe.

---

**Q2.** `$` aur `#` prompt mein kya fark hai?

- A) `$` = bash shell, `#` = zsh shell — shell type batata hai
- B) `$` = normal user, `#` = root user — privilege level batata hai
- C) `$` = writable directory, `#` = read-only directory
- D) `$` = interactive mode, `#` = script mode

✅ **Sahi Jawab: B**
> `$` = normal user. `#` = root. hamesha prompt check karo — agar `#` hai toh root ho — be careful. normal kaam `$` pe karo.

---

**Q3.** `chmod 644 file.txt` mein owner ko kya permissions milti hain?

- A) sirf read — `4` = r
- B) read aur execute — `4+1 = 5`
- C) poori permissions — `7 = rwx`
- D) read aur write — `4+2 = 6 = rw-`

✅ **Sahi Jawab: D**
> `644` = owner:6, group:4, others:4. `6` = `rw-` = read+write. `4` = `r--` = sirf read. typical config file permissions — owner edit kar sakta hai, baaki padh sakte hain.

---

**Q4.** `sudo` aur `su` mein kya fark hai?

- A) `sudo` ek command root ki tarah chalata hai — tumhara password maangta hai. `su` poora user switch karta hai — target user ka password maangta hai
- B) `sudo` permanent root ban jaata hai, `su` temporary
- C) `sudo` sirf file operations ke liye, `su` network operations ke liye
- D) dono same hain — sirf syntax alag hai

✅ **Sahi Jawab: A**
> `sudo command` = us command ke liye root powers. tumhara khud ka password. `su username` = us user mein switch — us user ka password chahiye. `sudo su` = root shell — root ka password nahi chahiye agar sudo rights hain.

---

**Q5.** `chmod 777 file.txt` kyun dangerous hai?

- A) file corrupt ho jaati hai — 7 invalid permission value hai
- B) file permanently locked ho jaati hai — remove nahi ho sakti
- C) sirf root ke liye dangerous — normal user ke liye theek hai
- D) sab ke liye read, write, execute — koi bhi file modify, replace, ya malicious code execute kar sakta hai

✅ **Sahi Jawab: D**
> `777` = `rwxrwxrwx` = sab ke liye sab kuch. production server pe yeh = anyone can modify or execute. major security vulnerability. hamesha minimum required permissions do.

---

**Q6.** `/etc/shadow` file ko kyon sirf root access kar sakta hai?

- A) kyunki yeh file bahut badi hai — normal users ke liye slow hogi
- B) kyunki isme hashed passwords hain — access milne pe password cracking possible ho sakti hai
- C) kyunki yeh system backup file hai — accidental modification se bachane ke liye
- D) normal users ko `/etc/` directory access nahi hoti kisi bhi file ke liye

✅ **Sahi Jawab: B**
> `/etc/shadow` = hashed passwords. agar readable by all ho — koi bhi hash download karke offline crack karne ki koshish kar sakta hai. isliye `root` only.

---

**Q7.** `chmod u+x script.sh` ka matlab kya hai?

- A) unknown users ko execute permission do
- B) update karo file — latest version se
- C) un-executable banao — execute permission hata do
- D) user (owner) ko execute permission add karo

✅ **Sahi Jawab: D**
> `u` = user/owner. `+` = add. `x` = execute. owner ko execute permission dedo. script run karna hai? pehle `chmod +x script.sh` — phir `./script.sh`.

---

**Q8.** `id` command kya output deta hai?

- A) uid, gid, aur sare groups jisme current user hai
- B) current user ka government ID ya username
- C) installed packages ki count — system ID
- D) network interface ka hardware ID (MAC address)

✅ **Sahi Jawab: A**
> `id` = complete identity. uid (user ID), gid (primary group ID), groups (sare groups). `sudo` group mein hona = sudo powers hain user ko.

---

**Q9.** `ls -l` mein `-rwxr-xr--` ka full matlab kya hai?

- A) regular file, owner: rwx, group: r-x, others: r--
- B) directory, owner: rwx, group: r-x, others: r--
- C) link file, sirf owner access kar sakta hai
- D) hidden file, root ke liye rwx, baaki ke liye r--

✅ **Sahi Jawab: A**
> pehla `-` = regular file (`d` hota toh directory). phir teen groups of 3: owner=`rwx`, group=`r-x`, others=`r--`. numeric mein = `754`.

---

**Q10.** `chown -R kali /var/www/` kya karta hai?

- A) `/var/www/` ka owner check karta hai — report generate karta hai
- B) sirf `/var/www/` folder ka owner `kali` karta hai — andar files nahi
- C) `/var/www/` aur us ke andar sari files/folders ka owner `kali` karta hai
- D) `kali` user ko `/var/www/` access allow karta hai bina ownership change kiye

✅ **Sahi Jawab: C**
> `-R` = recursive. folder aur uske andar sab kuch — sari files, sare subfolder — sabka owner `kali` ho jaata hai. web server setup mein common use.

---

**Q11.** `/etc/passwd` mein `x` ka matlab kya hai?

- A) user disabled hai — `x` = locked
- B) password `/etc/shadow` mein stored hai — `x` placeholder hai
- C) user ko root permissions hain — `x` = extra privileges
- D) user ko shell access nahi hai — `x` = no login

✅ **Sahi Jawab: B**
> `/etc/passwd` mein password field mein `x` matlab actual hashed password `/etc/shadow` mein hai. pehle `/etc/passwd` mein hi rehta tha — security ke liye `/etc/shadow` mein move kiya gaya.

---

**Q12.** sensitive private key file ke liye best permission kya hai?

- A) `644` — owner read/write, others read only
- B) `755` — owner all, others read/execute
- C) `600` — sirf owner read/write, baaki koi nahi
- D) `777` — sabke liye accessible — hamesha available

✅ **Sahi Jawab: C**
> `600` = `rw-------`. sirf owner read/write kar sakta hai. SSH private keys ke liye `600` mandatory hai — actually SSH connect hi nahi karta agar key ka permission `600` nahi hoga.

---

**Q13.** `sudo su` ke baad kaunsi command normal user mein wapas laayegi?

- A) `sudo exit`
- B) `return`
- C) `exit`
- D) `logout user`

✅ **Sahi Jawab: C**
> `exit` = current shell se bahar. `sudo su` se root shell khuli — `exit` type karo — wapas normal user. ya `Ctrl + D`.

---

**Q14.** ek script file hai — run karna hai — `Permission denied` error aa raha hai — kya karo?

- A) `sudo rm script.sh` — purani file hata ke dobara banao
- B) `chmod +x script.sh` — execute permission do — phir `./script.sh`
- C) `cat script.sh | bash` — file read karke bash ko do
- D) `run script.sh` — `./` ki jagah `run` use karo

✅ **Sahi Jawab: B**
> `Permission denied` = execute bit set nahi. `chmod +x script.sh` — `x` add karo — phir `./script.sh` se run karo. `cat | bash` bhi technically kaam karta hai lekin proper tarika nahi.

---

**Q15.** `whoami` aur `id` mein kya fark hai?

- A) `whoami` = username sirf. `id` = uid, gid, groups — complete identity information
- B) `whoami` = all users on system. `id` = current user only
- C) `whoami` = root ke liye. `id` = normal users ke liye
- D) dono same hain — sirf output format alag hai

✅ **Sahi Jawab: A**
> `whoami` = sirf username print. `id` = uid, gid, sare groups. quick check ke liye `whoami`, complete info ke liye `id`.

---

## 🎯 Task — Topic 5.7 — Permissions Explore Karo

**task naam: "permissions ko haath lagao"**

```bash
# 1. current user ka pata lagao
whoami
id

# 2. home directory ka permission dekho
ls -la ~

# 3. ek test file banao
touch test_permissions.txt
ls -l test_permissions.txt

# 4. permissions note karo — default kya hai?

# 5. permissions change karo
chmod 600 test_permissions.txt
ls -l test_permissions.txt
# sirf owner ke liye — kya dikhta hai?

# 6. execute permission do
chmod +x test_permissions.txt
ls -l test_permissions.txt

# 7. /etc/passwd dekho
cat /etc/passwd | head -5
# pehli 5 lines — format samjho

# 8. shadow ko try karo
cat /etc/shadow
# error aayega — kyun? (root access chahiye)

# 9. sudo se try karo
sudo cat /etc/shadow | head -3
# ab kya aaya?

# 10. ek script banao aur run karo
echo '#!/bin/bash' > myscript.sh
echo 'echo "Script chal rahi hai!"' >> myscript.sh
chmod +x myscript.sh
./myscript.sh
```

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.7 COMPLETE — USERS AUR PERMISSIONS
   ⬇️  Neeche hai Topic 5.8
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.8 — Networking Commands — Network Ko Terminal Se Dekhna

---

### Chapter 3 yaad hai?

chapter 3 mein humne networking theory seekhi — IP address, MAC address, ports, protocols, DNS, packets.

ab woh sab practical hoga. terminal se network ko dekho, samjho, explore karo.

> **yeh commands ethical hacking ka daily kaam hain. target machine ke baare mein jaanna hai — network commands se shuru hota hai.**

---

### `ip` — Network Interface Information

**modern Linux mein `ip` command preferred hai:**

```bash
ip addr
```

ya short form:
```bash
ip a
```

output:
```
1: lo: <LOOPBACK,UP> mtu 65536
    link/loopback 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo

2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500
    link/ether 08:00:27:ab:cd:ef brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.105/24 brd 192.168.1.255 scope global eth0
```

dekho kya mila:
- `lo` = loopback interface — `127.0.0.1` — machine apne aap se baat karti hai
- `eth0` = ethernet interface — `192.168.1.105` — tumhara actual IP
- `08:00:27:ab:cd:ef` = MAC address

**routing table dekho:**
```bash
ip route
```
output:
```
default via 192.168.1.1 dev eth0
192.168.1.0/24 dev eth0
```
`192.168.1.1` = tumhara gateway (router) — yahan se internet milta hai.

---

### `ifconfig` — Purana Tarika (Abhi Bhi Use Hota Hai)

```bash
ifconfig
```

`ip addr` jaisi info deta hai — lekin purana tool. abhi bhi bahut se tutorials aur professionals use karte hain.

agar available nahi:
```bash
sudo apt install net-tools
```

---

### `ping` — Kya Woh Machine Online Hai?

```bash
ping google.com
```

output:
```
PING google.com (142.250.77.46): 56 data bytes
64 bytes from 142.250.77.46: icmp_seq=0 ttl=116 time=12.4 ms
64 bytes from 142.250.77.46: icmp_seq=1 ttl=116 time=11.8 ms
```

matlab: google.com reachable hai — reply aa raha hai — `12ms` latency.

**sirf kuch baar ping karo:**
```bash
ping -c 4 google.com
```
`-c 4` = sirf 4 packets bhejo phir rok do.

**local machine test:**
```bash
ping 127.0.0.1
```
loopback — tumhara machine khud reply karega — network stack sahi kaam kar raha hai.

**ping se kya pata chalta hai:**
- machine online hai ya nahi
- latency kitni hai
- packet loss hai kya

> **note:** kuch servers ICMP (ping) block karte hain — reply nahi aata matlab machine off nahi hai necessarily.

---

### `netstat` — Network Connections Dekho

```bash
netstat -tulpn
```

options:
- `-t` = TCP connections
- `-u` = UDP connections
- `-l` = listening ports (wait kar raha hai connections ke liye)
- `-p` = process naam dikhao
- `-n` = numeric format (hostnames resolve mat karo)

output:
```
Proto  Local Address    Foreign Address   State     PID/Program
tcp    0.0.0.0:22       0.0.0.0:*         LISTEN    1234/sshd
tcp    0.0.0.0:80       0.0.0.0:*         LISTEN    5678/apache2
```

yahan dikhega — **kaun se ports open hain, kaunsa program chal raha hai us port pe.**

agar `netstat` available nahi:
```bash
sudo apt install net-tools
```

---

### `ss` — `netstat` Ka Modern Version

```bash
ss -tulpn
```

same options — same output — lekin faster aur modern:

```
Netid  State   Local Address:Port
tcp    LISTEN  0.0.0.0:22         users:(("sshd",pid=1234))
tcp    LISTEN  0.0.0.0:80         users:(("apache2",pid=5678))
```

---

### `curl` — URL Se Data Fetch Karo

```bash
curl https://example.com
```

website ka HTML content terminal mein print ho jaayega.

**sirf headers dekho:**
```bash
curl -I https://example.com
```

output:
```
HTTP/2 200
content-type: text/html; charset=UTF-8
server: ECS
```

**server type, response code — yeh information security assessment mein use hoti hai.**

**file download karo:**
```bash
curl -o output.html https://example.com
```

**kisi IP pe request karo:**
```bash
curl http://192.168.1.1
```

---

### `wget` — Files Download Karo

```bash
wget https://example.com/file.zip
```

file seedha current folder mein download ho jaayega.

**resume interrupted download:**
```bash
wget -c https://example.com/bigfile.zip
```

`curl` vs `wget`:
- `curl` = flexible — APIs, custom headers, many protocols
- `wget` = download focused — large files, recursive download

---

### `host` aur `nslookup` — DNS Queries

---

> 🔁 **Ruko — Chapter 3 yaad karo**
>
> yeh section samajhne se pehle ek second ruko.
>
> Chapter 3 mein humne **DNS** padha tha — Topic 3.6. yaad hai? "Internet Ka Phone Book" wala?
>
> wahan humne seekha tha —
>
> - browser `google.com` samajhta hai. lekin internet **sirf IP addresses** samajhta hai.
> - toh jab tum `google.com` type karte ho — pehle ek **DNS server** se poochha jaata hai: _"is naam ka IP kya hai?"_
> - DNS server jawab deta hai: `142.250.195.78` — phir browser wahan jaata hai.
> - yeh sab **milliseconds** mein hota hai — tum notice bhi nahi karte.
> - DNS ka port hota hai **53**.
> - aur humne yeh bhi padha tha ki hacker **DNS Poisoning** karke galat IP daalta hai — tum `google.com` type karo aur pohncho attacker ki fake site pe.
> - aur **DNS Enumeration** se hacker kisi bhi site ke subdomains, servers, services — sab DNS se dhundh leta hai.
>
> ab yahan `host` aur `nslookup` commands exactly wahi kaam karte hain — **terminal se DNS query maarna.** browser ke bajaaye tum khud pooch rahe ho DNS server se — "bhai, is domain ka IP kya hai?" — aur seedha jawab aata hai.
>
> yeh commands basic lagti hain — lekin aage jab hum **Reconnaissance** (target ki information gather karna) seekhenge — tab yahi commands kaam aayengi pehle step mein. foundation abhi ban raha hai.

---

**Domain ka IP pata karo:**
```bash
host google.com
```
output:
```
google.com has address 142.250.77.46
google.com has IPv6 address 2404:6800:4009:82b::200e
```

```bash
nslookup google.com
```
similar info — zyada detailed.

---

### `traceroute` — Data Ka Raasta Dekho

```bash
traceroute google.com
```

tumhara packet google tak jaane mein kaunse servers se guzra — sab dikhata hai:

```
1  192.168.1.1 (router) 1.2ms
2  10.0.0.1 (ISP gateway) 8.3ms
3  ...
...
15 google.com 45.2ms
```

agar installed nahi:
```bash
sudo apt install traceroute
```

---

### `hostname` — Machine Ka Naam

```bash
hostname
```
output:
```
kali
```

**IP of hostname:**
```bash
hostname -I
```

---

### `/etc/hosts` — Local DNS

```bash
cat /etc/hosts
```

output:
```
127.0.0.1    localhost
127.0.1.1    kali
```

yahan locally domain names define kar sakte ho — koi bhi domain kisi bhi IP pe redirect karo. DNS se pehle yahan check hota hai.

---

### `/etc/resolv.conf` — DNS Server Config

```bash
cat /etc/resolv.conf
```

output:
```
nameserver 8.8.8.8
nameserver 8.8.4.4
```

`8.8.8.8` = Google ka DNS server. yahi use hota hai domain resolve karne ke liye.

---

### ek line mein

> **`ip a` = apna IP. `ping` = reachable hai? `netstat`/`ss` = kaun se ports open. `curl` = HTTP request. `host` = DNS. `traceroute` = raasta dekho.**

---

## 🧠 MCQ Set — Topic 5.8

---

**Q1.** `ip addr` command kya dikhata hai?

- A) machine ke network interfaces aur unke IP, MAC addresses
- B) network pe connected sare devices ki IP list
- C) internet pe current connection ka status — upload/download speed
- D) routing table — kahan se kahan data jaata hai

✅ **Sahi Jawab: A**
> `ip addr` (ya `ip a`) = local machine ke network interfaces. `eth0`, `lo`, `wlan0` — har ek ka IP, MAC, status dikhata hai.

---

**Q2.** `127.0.0.1` kya hota hai?

- A) default gateway — router ka IP
- B) loopback address — machine apne aap se baat karti hai — always available
- C) DNS server ka IP — Google ka
- D) broadcast address — network pe sab devices ko message

✅ **Sahi Jawab: B**
> `127.0.0.1` = localhost = loopback. machine khud hi packet bhejti hai aur receive karti hai. network nahi chahiye. local development aur testing ke liye use hota hai.

---

**Q3.** `ping -c 4 192.168.1.1` kya karta hai?

- A) continuously ping karta rehta hai — manual stop se ruko
- B) port 4 pe ping karta hai — specific port test
- C) 4 seconds ke liye ping karta hai — time based
- D) sirf 4 ping packets bhejta hai phir automatically rok deta hai

✅ **Sahi Jawab: D**
> `-c 4` = count = 4 packets. bina `-c` ke ping indefinitely chalta hai Linux mein. `Ctrl + C` se band karo ya `-c` specify karo.

---

**Q4.** `netstat -tulpn` mein `-l` kya filter karta hai?

- A) sirf local connections — remote nahi
- B) sirf TCP connections — UDP nahi
- C) sirf listening ports — jo abhi connections accept kar rahe hain
- D) sirf localhost ke connections — external nahi

✅ **Sahi Jawab: C**
> `-l` = listening. woh ports jo koi service actively sun rahi hai — new connections ke liye wait kar rahi hai. `LISTEN` state mein hain. yeh important hai — open ports = potential attack surface.

---

**Q5.** `curl -I https://example.com` kya dikhata hai?

- A) sirf HTTP response headers — content body nahi
- B) website ka poora HTML content
- C) site ki images download karta hai
- D) site ka SSL certificate details

✅ **Sahi Jawab: A**
> `-I` = HEAD request. sirf headers aate hain — server type, response code, content-type, etc. full body nahi. reconnaissance mein useful — server kya chal raha hai pata karo bina full content download kiye.

---

**Q6.** `ss` command `netstat` se kab alag hai?

- A) `ss` sirf UDP connections dikhata hai — TCP ke liye `netstat`
- B) `ss` modern hai — faster, more features — `netstat` purana hai
- C) `ss` sirf Kali Linux mein hota hai — `netstat` universal hai
- D) dono same hain — sirf output format thoda alag hai

✅ **Sahi Jawab: B**
> `ss` = Socket Statistics — newer replacement for `netstat`. faster hai, zyada detail deta hai. `net-tools` package ke bina `netstat` nahi milta — `ss` by default available hai modern Linux mein.

---

**Q7.** `host google.com` kya karta hai?

- A) Google ka server directly ping karta hai — latency check
- B) Google ke saath TCP connection establish karta hai — handshake test
- C) DNS query karta hai — google.com ka IP address resolve karta hai
- D) google.com pe HTTP GET request bhejta hai

✅ **Sahi Jawab: C**
> `host` = DNS lookup tool. domain name leke DNS server se IP dhundhta hai. `host google.com` → `google.com has address 142.250.x.x`. quick DNS verification.

---

**Q8.** `/etc/hosts` file mein entry add karne se kya hota hai?

- A) permanently us host ke saath connection block ho jaata hai
- B) firewall rule ban jaata hai — woh host se traffic allow/deny
- C) system us host ko automatically ping karta hai connectivity ke liye
- D) us domain ke liye locally specific IP define ho jaati hai — DNS se pehle yahan check hota hai

✅ **Sahi Jawab: D**
> `/etc/hosts` = local DNS override. `192.168.1.100 myserver.local` add karo — `myserver.local` seedha `192.168.1.100` pe jaayega bina DNS server ke. penetration testers aur developers dono use karte hain.

---

**Q9.** `traceroute` se kya pata chalta hai?

- A) specific website ka server location — country aur city
- B) source se destination tak ke raaste mein sare intermediate routers/hops
- C) destination server ka OS aur open ports
- D) network speed — bandwidth measurement end-to-end

✅ **Sahi Jawab: B**
> traceroute = path discovery. packet tumhare machine se destination tak jaate jaate kahan kahan se guzrta hai — sare hops dikhata hai latency ke saath. network troubleshooting aur mapping ke liye.

---

**Q10.** `wget -c https://example.com/file.zip` mein `-c` ka matlab?

- A) compressed format mein download karo — smaller file
- B) certificate verify mat karo — self-signed sites ke liye
- C) continue — interrupted download resume karo — pehle se download hua part dobara nahi lega
- D) count — download speed measure karo

✅ **Sahi Jawab: C**
> `-c` = continue. bada file download ho raha tha — internet gaya — phir aaya. `wget -c` se wahan se continue karega jahan ruka tha. sab naya download nahi hoga.

---

**Q11.** `ip route` ka output mein "default via 192.168.1.1" ka matlab?

- A) `192.168.1.1` default gateway hai — internet ka traffic yahan se jaata hai
- B) `192.168.1.1` default DNS server hai
- C) `192.168.1.1` DHCP server hai — IPs wahan se milti hain
- D) `192.168.1.1` blocked IP hai — traffic route nahi hoga wahan

✅ **Sahi Jawab: A**
> default route = gateway. tumhara machine jab internet pe jaata hai — sab kuch pehle `192.168.1.1` (router) pe jaata hai — woh aage bhejta hai. yahi default gateway hai.

---

**Q12.** `curl -o file.html https://example.com` kya karta hai?

- A) example.com ka HTML terminal mein print karta hai
- B) example.com ka content `file.html` mein save karta hai
- C) `file.html` ko example.com pe upload karta hai
- D) example.com se sirf headers fetch karta hai aur `file.html` mein save karta hai

✅ **Sahi Jawab: B**
> `-o file.html` = output file specify karo. URL ka content us file mein save hoga terminal pe print hone ki jagah. download karna ho — `-o` use karo.

---

**Q13.** `ifconfig` available nahi hai — kaise install karein?

- A) `sudo apt install ifconfig`
- B) `sudo apt install network-manager`
- C) `pip install ifconfig`
- D) `sudo apt install net-tools`

✅ **Sahi Jawab: D**
> `ifconfig` `net-tools` package ka part hai. `sudo apt install net-tools` — phir `ifconfig` available. modern Kali mein `ip` command prefer karni chahiye — `net-tools` purana hai.

---

**Q14.** ping se machine online confirm hona 100% reliable kyun nahi?

- A) kuch servers/firewalls ICMP ping packets block karte hain — reply nahi aata matlab machine off nahi necessarily
- B) ping sirf localhost ke saath kaam karta hai — external machines ke liye accurate nahi
- C) ping sirf IPv4 pe kaam karta hai — IPv6 machines detect nahi hoti
- D) ping sirf Kali se kaam karta hai — Windows machines respond nahi karte

✅ **Sahi Jawab: A**
> many servers ICMP ko firewall se block karte hain — security ke liye. no ping reply ≠ machine offline. aur bhi methods hain — TCP SYN scan, HTTP request, etc.

---

**Q15.** `/etc/resolv.conf` mein kya stored hota hai?

- A) network interface configuration — IP, gateway, subnet
- B) local hostname mappings — `/etc/hosts` jaisi
- C) DNS server addresses — domain resolution ke liye kaun se servers use karo
- D) firewall rules — allowed aur blocked IPs

✅ **Sahi Jawab: C**
> `/etc/resolv.conf` = DNS configuration. `nameserver 8.8.8.8` matlab "DNS queries 8.8.8.8 pe bhejo." yahan apna DNS server change kar sakte ho.

---

## 🎯 Task — Topic 5.8 — Apna Network Explore Karo

**task naam: "apna network map karo"**

```bash
# 1. apna IP address dekho
ip a

# tumhara eth0 ya wlan0 ka IP note karo

# 2. gateway pata karo
ip route
# "default via X.X.X.X" — woh X.X.X.X tumhara router hai

# 3. internet connection test karo
ping -c 4 8.8.8.8

# 4. domain test karo
ping -c 3 google.com

# 5. DNS check karo
host google.com
host kali.org

# 6. open ports dekho
ss -tulpn

# ya
netstat -tulpn 2>/dev/null || sudo apt install -y net-tools && netstat -tulpn

# 7. curl test karo
curl -I https://www.google.com

# 8. wget se kuch download karo
wget -O /tmp/test.html https://example.com
cat /tmp/test.html | head -20

# 9. /etc/hosts dekho
cat /etc/hosts

# 10. resolv.conf dekho
cat /etc/resolv.conf
```

**note karo:**
- tumhara IP kya hai?
- gateway IP kya hai?
- kaunse ports open hain?
- DNS server IP kya hai?

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.8 COMPLETE — NETWORKING COMMANDS
   ⬇️  Neeche hai Topic 5.9
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.9 — Piping aur Redirection — Commands Ko Milao

---

### yeh concept Linux ki asli power hai

abhi tak tumne commands akele chalaye. ek command — ek output.

ab kuch alag sikhenge —

> **commands ko ek doosre ke saath connect karo. ek ka output doosre ka input. chain banao.**

yeh concept hacking mein **everywhere** use hota hai — tool ka output grep se filter karo, file mein save karo, doosre tool ko do.

---

### `|` — Pipe — Output Ko Doosre Command Ko Do

**Pipe symbol `|`** — ek command ka output doosre command ka input ban jaata hai.

```bash
command1 | command2
```

**example — `ls` ka output `grep` ko do:**
```bash
ls /etc | grep "passwd"
```

`ls /etc` → sari files list ki → pipe → `grep "passwd"` ne filter kiya → sirf `passwd` wali lines dikhi.

**example — badi file mein search karo aur less se dekho:**
```bash
cat /etc/passwd | less
```

**example — processes mein search karo:**
```bash
ps aux | grep "apache"
```

**example — lines count karo:**
```bash
ls /etc | wc -l
```
`/etc` mein kitni files hain — count karke batao.

---

### `>` — Output Ko File Mein Save Karo (Overwrite)

```bash
command > file.txt
```

command ka output terminal pe print hone ki jagah — file mein chala jaata hai.

```bash
ls -la > filelist.txt
```

`filelist.txt` create hogi jisme `ls -la` ka output hoga.

**⚠️ `>` existing file ko overwrite karta hai.** pehle se kuch tha — gone.

---

### `>>` — Append Karo (Add At End)

```bash
command >> file.txt
```

existing file ke end mein add karo — overwrite nahi hoga.

```bash
echo "pehli line" > notes.txt
echo "doosri line" >> notes.txt
cat notes.txt
```

output:
```
pehli line
doosri line
```

---

### `<` — File Ko Input Do

```bash
command < file.txt
```

file ka content command ko input ke roop mein do.

```bash
wc -l < file.txt
```

`file.txt` ka content `wc -l` ko milega — lines count karega.

---

### `2>` — Error Output Ko File Mein

Linux mein do types ke output hote hain:
- **stdout (1)** = normal output
- **stderr (2)** = error output

```bash
command 2> errors.txt
```

error messages `errors.txt` mein chale jaayenge — terminal clean rahega.

```bash
command 2>/dev/null
```

`/dev/null` = Linux ka "dustbin" — kuch bhi bhejo, gayab. errors hide karne ke liye.

**dono output ek file mein:**
```bash
command > output.txt 2>&1
```
`2>&1` = stderr ko stdout ke saath merge karo.

---

### `grep` — Filter Karo

grep pipe ke saath bahut use hota hai:

```bash
ps aux | grep "ssh"
```
running processes mein se sirf ssh wale dhundho.

```bash
cat /var/log/syslog | grep "error" | tail -20
```
log file → error wali lines → aakhri 20.

---

### `sort` — Sort Karo

```bash
sort file.txt
```
alphabetically sort karega.

```bash
sort -n numbers.txt
```
numerically sort.

```bash
sort -r file.txt
```
reverse order.

```bash
ls -la | sort -k5 -n
```
`ls` output ko size (5th column) ke hisaab se numerically sort karo.

---

### `uniq` — Duplicate Hatao

```bash
sort file.txt | uniq
```

pehle sort karo — phir duplicates hata do.

```bash
sort file.txt | uniq -c
```
har unique line kitni baar aayi — count ke saath.

---

### `cut` — Specific Columns Nikalo

```bash
cut -d: -f1 /etc/passwd
```
`-d:` = delimiter colon. `-f1` = pehla field. `/etc/passwd` se sirf usernames nikalo.

output:
```
root
daemon
kali
...
```

---

### `tee` — Terminal Pe Bhi Dikho, File Mein Bhi Save Ho

```bash
command | tee output.txt
```

output terminal pe bhi dikhega aur file mein bhi save hoga — dono ek saath.

```bash
ping -c 4 google.com | tee ping_results.txt
```

---

### Practical Chain — Real Example

ek realistic example jo hacking mein use hota hai:

```bash
cat /etc/passwd | cut -d: -f1 | sort | uniq
```

step by step:
1. `cat /etc/passwd` → poori file print
2. `cut -d: -f1` → sirf pehla field (username) nikalo
3. `sort` → alphabetically sort karo
4. `uniq` → duplicates hata do

result: sare unique usernames — cleanly sorted.

---

### `/dev/null` — Dustbin

```bash
command > /dev/null 2>&1
```

output aur errors dono dustbin mein — kuch bhi terminal pe nahi dikhega. background scripts mein use hota hai jab output ki zarurat nahi.

---

### ek line mein

> **`|` = output ko agla command ko do. `>` = file mein save (overwrite). `>>` = append. `2>` = errors ko redirect. `grep` = filter. `sort` = sort. `uniq` = duplicates hata do.**

---

## 🧠 MCQ Set — Topic 5.9

---

**Q1.** `ls /etc | grep "conf"` kya karta hai?

- A) `/etc` mein "conf" naam ka folder banata hai
- B) `grep` command ko `/etc` directory ka configuration update karta hai
- C) `/etc` mein "conf" word dhundh ke woh files delete karta hai
- D) `/etc` ke contents list karta hai, phir sirf "conf" wali lines filter karta hai

✅ **Sahi Jawab: D**
> `ls /etc` ka output pipe se `grep "conf"` ko gaya — sirf woh lines dikhi jisme "conf" tha. do commands mila ke useful filter bana.

---

**Q2.** `>` aur `>>` mein kya fark hai?

- A) `>` = overwrite — existing content replace karta hai. `>>` = append — existing ke baad add karta hai
- B) `>` = append, `>>` = overwrite — ulta
- C) dono same hain — sirf file creation ke liye alag syntax
- D) `>` = file mein write, `>>` = terminal pe print

✅ **Sahi Jawab: A**
> `>` = overwrite — file exist karti hai toh erase karke naya likh do. `>>` = append — existing ke baad add karo. galat use = important data gone. hamesha sochlo kaunsa chahiye.

---

**Q3.** `/dev/null` kya hai?

- A) ek real folder jahan deleted files temporarily jaati hain
- B) network null device — offline testing ke liye
- C) default NULL device — kuch bhi bhejo, seedha discard — Linux ka dustbin
- D) debug device — errors wahan log hoti hain

✅ **Sahi Jawab: C**
> `/dev/null` = virtual device jo kuch bhi accept karta hai aur discard karta hai. `command > /dev/null` = output mujhe mat dikhao. scripts mein unnecessary output suppress karne ke liye.

---

**Q4.** `2>&1` ka matlab kya hai?

- A) stderr ko stdin ko redirect karo
- B) command ko 2 baar run karo, output 1 file mein
- C) 2 processes start karo 1 command se
- D) stderr (2) ko stdout (1) ke saath merge karo — dono ek jagah jaate hain

✅ **Sahi Jawab: D**
> stderr (2) aur stdout (1) — dono alag streams hain. `2>&1` = "stderr ko waheen bhejo jahan stdout ja raha hai." `> output.txt 2>&1` = dono output.txt mein.

---

**Q5.** `cat /etc/passwd | cut -d: -f1` kya karta hai?

- A) `/etc/passwd` mein `:` ko `/` se replace karta hai
- B) `/etc/passwd` ko cut karke delete karta hai pehla field
- C) colon ko delimiter manke pehla field (username) nikalta hai har line se
- D) pehli line sirf nikalta hai — `-f1` = first line

✅ **Sahi Jawab: C**
> `cut -d: -f1` = delimiter colon, field 1 nikalo. `/etc/passwd` format colon separated hai — pehla field username hai. yeh command sare usernames cleanly extract karta hai.

---

**Q6.** `sort file.txt | uniq -c` kya dikhata hai?

- A) file ko sort karke unique files count karta hai
- B) sorted unique lines — har line ke saath kitni baar aayi uska count
- C) duplicate lines sirf dikhata hai — unique nahi
- D) file ki line count sorted format mein

✅ **Sahi Jawab: B**
> `sort` pehle sort karta hai (duplicate adjacent hone ke liye). `uniq -c` = unique lines count ke saath. `5 error` matlab "error" line 5 baar aayi. log analysis mein common pattern.

---

**Q7.** `ping -c 4 google.com | tee results.txt` kya karta hai?

- A) ping output terminal pe bhi dikhata hai aur results.txt mein bhi save karta hai
- B) ping output sirf results.txt mein save karta hai — terminal pe nahi dikhta
- C) results.txt se ping command run karta hai
- D) ping output ke 4 copies results.txt mein save karta hai

✅ **Sahi Jawab: A**
> `tee` = T junction. terminal pe bhi, file mein bhi — dono jagah. bina tee ke ya toh terminal dikhta ya file mein jaata. tee se dono simultaneously.

---

**Q8.** `command 2>/dev/null` kyun use karte hain?

- A) command ko debug mode mein chalane ke liye — detailed errors
- B) command output ko double speed pe show karne ke liye
- C) errors ko suppress karne ke liye — terminal pe error messages nahi dikhne
- D) command ko background mein chalane ke liye

✅ **Sahi Jawab: C**
> `2>/dev/null` = stderr dustbin mein bhejo. scripts mein jab errors expected hain aur show nahi karni — use karo. clean output milti hai. terminal cluttered nahi hota.

---

**Q9.** `cat file.txt | wc -l` aur `wc -l < file.txt` mein kya fark hai?

- A) pehla kaam karta hai doosra nahi — `<` Kali mein supported nahi
- B) dono same result dete hain — sirf syntax alag hai
- C) pehla content print bhi karta hai, doosra nahi
- D) pehla file.txt modify karta hai, doosra nahi

✅ **Sahi Jawab: B**
> dono same result dete hain — file ki lines count karo. `cat | wc -l` = pipe se. `wc -l < file.txt` = input redirection se. practically dono same hain is case mein.

---

**Q10.** `ps aux | grep "ssh" | grep -v "grep"` mein doosra `grep` kyun hai?

- A) double filtering ke liye — accuracy improve karta hai
- B) SSH processes ko version se filter karna
- C) extra security — duplicate results hata do
- D) `grep "ssh"` command khud `ps` output mein dikhti hai — `grep -v "grep"` se woh hata do

✅ **Sahi Jawab: D**
> `grep` command khud bhi process hai — `ps aux` mein dikhti hai "grep ssh" ke saath. `grep -v "grep"` = "grep" word wali lines hata do — sirf actual SSH processes bachti hain. common pattern.

---

**Q11.** `sort -k5 -n` ka matlab kya hai?

- A) 5th character se sort karo — alphabetically
- B) 5th column (field) se numerically sort karo
- C) top 5 results dikhao — sorted
- D) 5 seconds ke liye sort karo phir stop

✅ **Sahi Jawab: B**
> `-k5` = 5th field/column. `-n` = numeric sort (1, 2, 10... — alphabetic mein "10" "2" se pehle aata). `ls -la | sort -k5 -n` = files ko size ke hisaab se sort karo.

---

**Q12.** `echo "kali" | md5sum` kya karta hai?

- A) "kali" word ka MD5 hash calculate karta hai — password cracking practice
- B) "kali" naam se ek folder banata hai aur MD5 checksum save karta hai
- C) Kali Linux version ka MD5 check karta hai — integrity verify
- D) "kali" ko base64 mein encode karta hai

✅ **Sahi Jawab: A**
> `echo "kali"` output pipe se `md5sum` ko gaya — MD5 hash banaya. yeh is liye interesting hai kyunki aage password hashing aur cracking sikhenge — yahi foundation hai.

---

**Q13.** `ls -la /etc/ 2>/dev/null | grep "^-rw"` kya karta hai?

- A) `/etc` mein sare directories list karta hai
- B) `/etc` mein read-write permissions wali files dhundh ke delete karta hai
- C) errors suppress karta hai, sirf regular files (`-rw`) dikhata hai
- D) `/etc` ka listing ek file mein save karta hai

✅ **Sahi Jawab: C**
> `2>/dev/null` = permission errors suppress. `grep "^-rw"` = sirf woh lines jo `-rw` se shuru hoon — regular files (not directories `d`, not links `l`). chained filtering.

---

**Q14.** Pipe `|` ka flow kaunsa direction mein hai?

- A) right se left — output pehle, input baad mein process hota hai
- B) bidirectional — dono commands ek saath communicate karte hain
- C) depends karta hai command pe — kuch left-to-right, kuch right-to-left
- D) left se right — left command ka output right command ka input ban jaata hai

✅ **Sahi Jawab: D**
> `command1 | command2` — left (command1) ka stdout → right (command2) ka stdin. hamesha left se right. `ls | grep` = ls ka output grep ko milta hai.

---

**Q15.** `cat /var/log/auth.log | grep "Failed" | tail -20 > recent_failures.txt` kya karta hai?

- A) auth.log se "Failed" wali lines filter karo, aakhri 20 lo, file mein save karo
- B) auth.log ko delete karta hai aur new file banata hai recent_failures.txt
- C) last 20 auth attempts monitor karta hai real-time mein
- D) failed passwords ko `/var/log/auth.log` se `recent_failures.txt` mein move karta hai

✅ **Sahi Jawab: A**
> chain: `cat` (read) → `grep "Failed"` (filter) → `tail -20` (last 20) → `> recent_failures.txt` (save). real-world log analysis ka example — failed login attempts dhundho aur save karo.

---

## 🎯 Task — Topic 5.9 — Pipe aur Redirection Practice

**task naam: "commands ko milao"**

```bash
# 1. basic pipe
ls /etc | grep "conf" | head -10

# 2. file mein save karo
ls -la ~ > home_contents.txt
cat home_contents.txt

# 3. append karo
echo "--- System Info ---" >> home_contents.txt
uname -a >> home_contents.txt
cat home_contents.txt

# 4. errors suppress karo
ls /root 2>/dev/null
ls /root 2>/dev/null || echo "Access Denied — expected!"

# 5. usernames nikalo
cat /etc/passwd | cut -d: -f1 | sort

# 6. lines count karo
cat /etc/passwd | wc -l

# 7. tee use karo
ip a | tee network_info.txt
cat network_info.txt

# 8. running processes mein search
ps aux | grep "bash" | grep -v "grep"

# 9. sort use karo
echo -e "banana\napple\ncherry\napple\nbanana" | sort | uniq -c | sort -rn

# 10. chaining — log analysis
sudo cat /var/log/auth.log 2>/dev/null | grep "session" | tail -5
```

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.9 COMPLETE — PIPING AUR REDIRECTION
   ⬇️  Neeche hai Topic 5.10
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.10 — Process Management — System Pe Kya Chal Raha Hai

---

### process kya hoti hai?

jab tum koi program chalate ho — terminal ho, browser ho, ya koi tool — woh ek **process** ban jaata hai.

ek process = ek running program.

```
Browser khola → Browser process start
Terminal khola → Terminal process start
Nmap run kiya → Nmap process start
```

har process ka:
- ek unique **PID** (Process ID) hota hai
- ek parent process hoti hai jisne ise start kiya
- CPU aur RAM usage hoti hai
- ek owner user hota hai

---

### `ps` — Process List Dekho

```bash
ps
```

sirf current terminal ke processes dikhata hai — limited.

**sab processes dekho:**
```bash
ps aux
```

options:
- `a` = sab users ke processes
- `u` = detailed format (user, CPU, RAM)
- `x` = terminal se attached nahi wale bhi

output:
```
USER    PID  %CPU %MEM   COMMAND
root      1   0.0  0.1   /sbin/init
kali   1234   0.1  2.3   /usr/bin/python3 script.py
kali   2345   0.0  0.5   bash
```

---

### `top` — Live Process Monitor

```bash
top
```

real-time process monitor — CPU, RAM use dekho live:

```
Tasks: 156 total, 1 running
%Cpu: 2.3 us, 0.5 sy
MiB Mem: 3900 total, 1200 free

PID    USER    %CPU  %MEM  COMMAND
1234   root     25.0   5.1  python3
5678   kali      1.2   2.3  firefox
```

controls:
- `q` = quit
- `k` = kill process (PID daalo)
- `P` = CPU usage se sort karo
- `M` = Memory usage se sort karo
- `u` = specific user ke processes

---

### `htop` — Better Version of top

```bash
htop
```

colorful, interactive version:

```bash
sudo apt install htop
```

agar installed nahi. `htop` mein:
- colored bars — CPU, RAM visual
- mouse support
- F9 = kill process
- F10 = quit

---

### `kill` — Process Rokna

har process ka PID hota hai — us PID ko kill karo:

```bash
kill 1234
```

process ko politely terminate karne ke liye — SIGTERM signal bhejta hai. process apna cleanup kar sakti hai.

**force kill — process nahi sun rahi:**
```bash
kill -9 1234
```

`-9` = SIGKILL — instant termination — koi cleanup nahi. last resort.

**process ka PID pata karo:**
```bash
pgrep firefox
```

ya:
```bash
ps aux | grep firefox | grep -v grep
```

**naam se kill karo:**
```bash
pkill firefox
```

---

### `jobs`, `bg`, `fg` — Background aur Foreground

**Background mein process chalao — `&`:**
```bash
ping google.com > /dev/null &
```

`&` = background mein chalao — terminal free rahega.

output:
```
[1] 5678
```
`[1]` = job number, `5678` = PID

**jobs dekho:**
```bash
jobs
```
```
[1]+  Running    ping google.com > /dev/null &
```

**background se foreground mein lao:**
```bash
fg 1
```
`fg %1` = job number 1 ko foreground mein.

**foreground process ko background mein bhejo:**
`Ctrl + Z` = process pause karo
phir `bg 1` = background mein resume karo.

---

### `nohup` — Terminal Band Hone Pe Bhi Chalta Rahe

```bash
nohup python3 script.py &
```

terminal close karo — process chalta rahega. output `nohup.out` file mein jaata hai.

---

### `free` — RAM Dekho

```bash
free -h
```

output:
```
              total   used    free   available
Mem:           7.7G   3.2G    2.1G    4.1G
Swap:          2.0G   0.0G    2.0G
```

`-h` = human readable. RAM kitni hai, kitni use ho rahi hai, kitni free hai.

---

### `uptime` — System Kitne Waqt Se Chal Raha Hai?

```bash
uptime
```

output:
```
10:30:15 up 2 days, 4:15, 1 user, load average: 0.12, 0.15, 0.10
```

"2 days, 4:15" = system 2 din 4 ghante 15 minute se chal raha hai.

servers pe uptime = stability measure.

---

### `df` — Disk Space Dekho

```bash
df -h
```

output:
```
Filesystem      Size  Used Avail Use%  Mounted on
/dev/sda1        79G   15G   60G  20%  /
tmpfs           3.9G     0  3.9G   0%  /dev/shm
```

disk kitna bhar gaya — percentage mein.

---

### `du` — Folder Ka Size Dekho

```bash
du -sh /home/kali/
```

`-s` = summary (total sirf). `-h` = human readable.

**sabse badi files dhundho:**
```bash
du -sh /home/kali/* | sort -rh | head -10
```

---

### ek line mein

> **`ps aux` = sab processes. `top`/`htop` = live monitor. `kill PID` = rokna. `kill -9` = force rokna. `&` = background. `jobs`/`fg`/`bg` = job control.**

---

## 🧠 MCQ Set — Topic 5.10

---

**Q1.** PID kya hota hai?

- A) Packet ID — network ke har packet ka unique number
- B) Port ID — open ports ke liye assigned number
- C) Process ID — har running program ka unique identifier
- D) Permission ID — file access control ke liye

✅ **Sahi Jawab: C**
> PID = Process ID. har process ka ek unique number. `kill 1234` matlab PID 1234 wali process ko terminate karo. `ps aux` mein PID column hota hai.

---

**Q2.** `ps aux` mein `a`, `u`, `x` ka kya matlab hai?

- A) all, user-owned, exclusive
- B) anonymous, user, extra verbose
- C) active, urgent, extended format
- D) all users' processes, user-format (detailed), including detached processes

✅ **Sahi Jawab: D**
> `a` = sab users ke processes. `u` = user-friendly detailed format. `x` = terminal se attach nahi wale processes bhi. teeno milake = poori process list.

---

**Q3.** `kill -9 PID` kab use karte hain?

- A) hamesha — yeh safest aur cleanest way hai
- B) sirf root processes ke liye — normal user processes ke liye -9 kaam nahi karta
- C) jab process normal `kill` se terminate nahi ho rahi — last resort
- D) jab process bahut zyada CPU use kar rahi ho — performance ke liye

✅ **Sahi Jawab: C**
> `kill` (SIGTERM) = process ko politely rokne ko kaho — cleanup kar sako. `-9` (SIGKILL) = instant forceful termination — koi cleanup nahi. pehle normal `kill` try karo — kaam na kare toh `-9`.

---

**Q4.** `top` mein `M` key dabane se kya hota hai?

- A) memory usage se sort karo — sabse zyada RAM use karne wala pehle
- B) main window minimize karo
- C) manual page kholo — help documentation
- D) monitored process mark karo — watch mode

✅ **Sahi Jawab: A**
> `top` mein `P` = CPU se sort, `M` = Memory se sort. kaunsa process sabse zyada RAM kha raha hai — `M` dabao — turant pata chalta hai.

---

**Q5.** Command ke baad `&` lagane se kya hota hai?

- A) command ko verbose mode mein chalata hai — detailed output
- B) command ko ek baar run karta hai phir automatic repeat — loop
- C) command ko root permissions se chalata hai — `sudo` jaisa
- D) command ko background mein chalata hai — terminal free rehta hai

✅ **Sahi Jawab: D**
> `command &` = background execution. terminal block nahi hota — aur kaam kar sakte ho. `jobs` se background jobs dekho, `fg` se foreground mein lao.

---

**Q6.** `Ctrl + Z` terminal mein kya karta hai?

- A) command undo karta hai — pichla kaam wapas
- B) terminal window close karta hai
- C) process ko pause karta hai — background mein suspended
- D) current command cancel karta hai — Ctrl+C jaisa

✅ **Sahi Jawab: C**
> `Ctrl + Z` = SIGTSTP = suspend. process ruk jaati hai — terminate nahi. phir `bg` se background mein resume, ya `fg` se foreground mein. `Ctrl + C` = terminate. `Ctrl + Z` = pause.

---

**Q7.** `htop` ka `top` se kya fayda hai?

- A) `htop` sirf root use kar sakta hai — better security
- B) `htop` zyada accurate CPU data deta hai — `top` approximate
- C) `htop` network usage dikhata hai — `top` nahi deta
- D) `htop` colorful, interactive, mouse support, easier to use — `top` plain aur older

✅ **Sahi Jawab: D**
> `htop` = modern `top`. colored bars, mouse click se interaction, process tree, easier kill interface. default available nahi hota — `sudo apt install htop`.

---

**Q8.** `nohup command &` kyun use karte hain?

- A) command ko no-hang mode mein chalao — faster execution
- B) terminal close hone pe bhi process chalta rahe — SSH disconnect pe bhi
- C) command ko no-output mode mein chalao — silent execution
- D) command ko non-root user se root ki tarah chalao

✅ **Sahi Jawab: B**
> `nohup` = no hangup. normally terminal close hone pe us session ke sare processes terminate hote hain. `nohup` se process chalta rehta hai. server pe long-running tasks ke liye.

---

**Q9.** `pkill firefox` kya karta hai?

- A) firefox ka PID dhundh ke kill karta hai — naam se seedha
- B) firefox ko pause karta hai — resume kia ja sakta hai
- C) firefox ko safely close karta hai — save dialog ke saath
- D) firefox ka config delete karta hai — clean uninstall

✅ **Sahi Jawab: A**
> `pkill naam` = naam se process dhundho aur kill karo. `kill PID` = specific PID se. `pkill` convenient hai — PID manually dhundhna nahi padta.

---

**Q10.** `free -h` command kya dikhata hai?

- A) free software ki list — open source packages
- B) RAM aur Swap usage — total, used, free, available
- C) free disk space — `df` jaisa
- D) free ports — available ports for use

✅ **Sahi Jawab: B**
> `free` = memory info. `-h` = human readable (GB, MB). RAM total, used, free, buffer/cache. swap bhi dikhata hai — RAM full hone pe swap use hoti hai.

---

**Q11.** `df -h` aur `du -sh` mein kya fark hai?

- A) `df` disk partitions ka space dikhata hai. `du` specific folder/files ka size dikhata hai
- B) `df` = disk format, `du` = disk usage — same cheez
- C) `df` sirf root ke liye, `du` all users ke liye
- D) `df` fast hai, `du` slow — bada fark nahi output mein

✅ **Sahi Jawab: A**
> `df` = disk filesystem — partitions kitna bhar gaye. `du` = disk usage — specific folder kitna space le raha hai. dono use hote hain alag purposes ke liye.

---

**Q12.** `pgrep ssh` kya karta hai?

- A) SSH service ko restart karta hai
- B) SSH connection test karta hai
- C) SSH ka PID dhundh ke print karta hai — bina poori process list ke
- D) SSH ke processes grep se count karta hai

✅ **Sahi Jawab: C**
> `pgrep naam` = sirf PID print karta hai — naam se match karke. `ps aux | grep ssh | grep -v grep | awk '{print $2}'` ka shortcut. `kill $(pgrep nginx)` — one liner process kill.

---

**Q13.** process `fg 1` kyun use karte hain?

- A) first process shuru karte waqt — `fg` = first go
- B) job number 1 ko background se foreground mein laane ke liye
- C) process ko fine-grained mode mein set karne ke liye
- D) process ko force terminate karne ke liye — `kill -9` jaisa

✅ **Sahi Jawab: B**
> `fg %1` ya `fg 1` = job number 1 ko foreground mein lao. `jobs` se job numbers dekho. background mein chala tha — interact karna hai — `fg` se foreground mein.

---

**Q14.** server pe `uptime` command kyun important hai?

- A) server ka physical location GPS coordinates deta hai
- B) server kitne time se chalu hai — stability aur reliability measure karta hai
- C) server ka current time zone pata karta hai
- D) server pe logged users ka total time calculate karta hai

✅ **Sahi Jawab: B**
> uptime = server kitne time se restart nahi hua. high uptime = stable server. security mein: target server ki uptime se OS version guess kar sakte hain — last patch/reboot kab tha.

---

**Q15.** `du -sh /home/kali/* | sort -rh | head -10` kya karta hai?

- A) home directory ki files ko size ke hisaab se sort karta hai — sabse badi pehle — top 10 dikhata hai
- B) home directory mein top 10 recently modified files dikhata hai
- C) 10 sabse purani files dhundh ke delete karta hai
- D) home directory ka total size 10 parts mein divide karke dikhata hai

✅ **Sahi Jawab: A**
> `du -sh` = har item ka size. `sort -rh` = reverse + human-readable sort (bada pehle). `head -10` = sirf top 10. disk space full ho raha hai — kaunsa folder sabse bada hai — yeh command.

---

## 🎯 Task — Topic 5.10 — Processes Ko Manage Karo

**task naam: "system ke andar jhankna"**

```bash
# 1. sab processes dekho
ps aux | head -20

# 2. live monitor kholna
top
# kuch seconds dekho — phir q dabao

# 3. htop install karo
sudo apt install -y htop
htop
# F10 se exit

# 4. background process chalao
ping google.com > /dev/null &
jobs

# 5. background process ka PID
pgrep ping

# 6. foreground mein lao
fg 1
# Ctrl+Z se pause karo

# 7. wapas background mein
bg 1

# 8. kill karo
pkill ping
jobs
# ab koi job nahi honi chahiye

# 9. RAM dekho
free -h

# 10. disk space dekho
df -h
du -sh /home/kali/
```

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.10 COMPLETE — PROCESS MANAGEMENT
   ⬇️  Neeche hai Topic 5.11
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.11 — File Search — Kuch Bhi Dhundho

---

### hacking mein search kyun zaroori hai?

imagine karo — ek target system pe tumhe access mila. system bada hai. files hazaron hain.

tumhe dhundna hai:
- koi config file jisme credentials hon
- koi backup file jisme sensitive data ho
- koi script jisme password hard-coded ho

manually dhundhna = ghanton ka kaam. terminal commands = seconds.

---

### `find` — Sabse Powerful Search Tool

```bash
find [kahan] [kya dhundho] [kya karo]
```

**naam se dhundho:**
```bash
find /home -name "passwords.txt"
```

**extension se:**
```bash
find / -name "*.conf" 2>/dev/null
```
sari `.conf` files — `2>/dev/null` = permission errors suppress.

**type se — sirf files:**
```bash
find /etc -type f
```
`-type f` = files. `-type d` = directories.

**size ke hisaab se:**
```bash
find / -size +100M 2>/dev/null
```
100 MB se badi files.

**permissions se:**
```bash
find / -perm -4000 2>/dev/null
```
SUID bit set wali files — privilege escalation ke liye important.

**recently modified:**
```bash
find /var -mtime -1 2>/dev/null
```
`-mtime -1` = pichle 1 din mein modify hua.

**find karke kuch karo:**
```bash
find /tmp -name "*.txt" -exec cat {} \;
```
har `.txt` file ko `cat` karo — `{}` = found file ka path. `\;` = command end.

---

### `locate` — Fast Search (Database Based)

```bash
locate passwd
```

`locate` ek pre-built database se search karta hai — bahut fast.

**limitation:** database regularly update hoti hai — naye files turant nahi milenge.

**database update karo:**
```bash
sudo updatedb
```

---

### `which` — Command Kahan Hai?

```bash
which python3
```

output:
```
/usr/bin/python3
```

command kaun si directory mein install hai — pata karo.

**example:**
```bash
which nmap
which wireshark
which metasploit
```

---

### `whereis` — Command Ke Sare Locations

```bash
whereis python3
```

output:
```
python3: /usr/bin/python3 /usr/lib/python3 /usr/share/man/man1/python3.1.gz
```

`which` se zyada detail — binary, source, man page — sab locations.

---

### `grep -r` — Content Mein Search Karo

```bash
grep -r "password" /etc/
```

`/etc/` mein sari files mein "password" word dhundho — recursive.

**common searches:**
```bash
grep -r "passwd" /etc/ 2>/dev/null
grep -r "secret" /var/www/ 2>/dev/null
grep -ri "api_key" /home/ 2>/dev/null
```

---

### `find` + `grep` — Powerful Combo

```bash
find /var/www -name "*.php" -exec grep -l "password" {} \;
```

PHP files dhundho — jo `password` contain karti hain — unke naam print karo.

---

### `type` — Command Ka Type Pata Karo

```bash
type ls
type cd
type python3
```

output:
```
ls is aliased to `ls --color=auto`
cd is a shell builtin
python3 is /usr/bin/python3
```

alias hai? builtin hai? external program hai?

---

### `stat` — File Ki Detailed Info

```bash
stat file.txt
```

output:
```
File: file.txt
Size: 980        Blocks: 8    IO Block: 4096  regular file
Inode: 1234567   Links: 1
Access: (0644/-rw-r--r--)  Uid: 1000(kali)   Gid: 1000(kali)
Access: 2024-01-15 10:30:00.000
Modify: 2024-01-15 10:30:00.000
Change: 2024-01-15 10:30:00.000
```

timestamps — file kab access hua, kab modify hua — forensics mein important.

---

### ek line mein

> **`find` = complex search — naam, type, size, permissions. `locate` = fast database search. `which` = command kahan. `grep -r` = content mein search. `stat` = file ki poori detail.**

---

## 🧠 MCQ Set — Topic 5.11

---

**Q1.** `find / -name "*.conf" 2>/dev/null` kya karta hai?

- A) `/` (root) se poori system mein `.conf` extension wali files dhundho — errors suppress karo
- B) current directory mein `.conf` files dhundho
- C) `.conf` files create karo — find = create
- D) `.conf` extension wali files ko `.txt` mein rename karo

✅ **Sahi Jawab: A**
> `find /` = root se poori system mein search. `-name "*.conf"` = is extension wali files. `2>/dev/null` = permission denied errors hide karo. configuration files dhundhne ka standard command.

---

**Q2.** `find / -perm -4000 2>/dev/null` kya dhundh raha hai?

- A) 4000 bytes se badi files
- B) 4000 se zyada links wali files
- C) sirf root ke readable files
- D) SUID bit set wali files — yeh files owner ki permissions se run hoti hain

✅ **Sahi Jawab: D**
> `-perm -4000` = SUID (Set User ID) bit. yeh files jab koi bhi run karta hai — file owner ki permissions se chalti hain. agar root-owned file pe SUID hai — privilege escalation possible. ethical hacking mein key finding.

---

**Q3.** `locate` aur `find` mein sabse bada fark kya hai?

- A) `locate` sirf home directory mein, `find` poori system mein
- B) `locate` files content search karta hai, `find` sirf naam se
- C) `locate` pre-built database use karta hai (fast, lekin stale ho sakti). `find` real-time search karta hai (slow, lekin accurate)
- D) `locate` root only, `find` all users

✅ **Sahi Jawab: C**
> `locate` = database. `find` = real-time. `locate` fast hai lekin agar file abhi create hui toh database mein nahi hogi — `updatedb` karo. `find` slow hai lekin hamesha current.

---

**Q4.** `which python3` kya batata hai?

- A) python3 ka executable file kis directory mein hai
- B) python3 installed hai ya nahi — yes/no
- C) python3 ka version number
- D) python3 se related sari files aur documentation

✅ **Sahi Jawab: A**
> `which` = command ka path. `/usr/bin/python3` = yahan python3 ka executable hai. agar multiple versions hain — `which` batata hai kaunsa default chal raha hai.

---

**Q5.** `find /home -type f -name "*.txt"` mein `-type f` kyun diya?

- A) sirf fast files dhundho — `-type f` = fast
- B) `-type f` format option hai — human readable output ke liye
- C) file type `.txt` confirm karo — extension verify
- D) sirf regular files dhundho — directories, links nahi — `.txt` naam wale

✅ **Sahi Jawab: D**
> `-type f` = regular files. bina iske directories ka naam bhi `.txt` ho sakta hai (unlikely lekin possible). `-type d` = directories. `-type l` = symbolic links.

---

**Q6.** `grep -ri "api_key" /var/www/` kya dhundh raha hai?

- A) `/var/www/` mein ek file `api_key` naam se — case insensitive
- B) API key generate karta hai aur `/var/www/` mein save karta hai
- C) `/var/www/` ki sari files mein "api_key" text — recursive, case insensitive
- D) `/var/www/` folder ki API permissions check karta hai

✅ **Sahi Jawab: C**
> `-r` = recursive. `-i` = case insensitive. `/var/www/` = web server files. web application files mein hard-coded API keys dhundh raha hai — common security issue.

---

**Q7.** `find /tmp -mtime -1` mein `-mtime -1` ka matlab?

- A) 1 MB se chhoti files
- B) pichle 1 din (24 ghante) mein modified files
- C) 1 link wali files — hard links
- D) 1 minute se zyada purani files

✅ **Sahi Jawab: B**
> `-mtime -1` = modification time, last 1 day. `-mtime +7` = 7 din se zyada purani. recent activity dhundhne ke liye useful — kya recently kisi ne files modify ki?

---

**Q8.** `find /etc -name "passwd" -exec cat {} \;` mein `{}` kya represent karta hai?

- A) empty string — placeholder
- B) user input ke liye prompt
- C) `find` se mili file ka path — `exec` command mein yahi insert hota hai
- D) error output — failed finds ko collect karta hai

✅ **Sahi Jawab: C**
> `{}` = found file ka path. `find` jab ek file dhundhe — `{}` ki jagah woh path daalo — phir command run karo. `\;` = ek ek file ke liye. `-exec cat {} \;` = har found file ko `cat` karo.

---

**Q9.** `stat` command kya information deta hai jo `ls -l` nahi deta?

- A) inode number, exact timestamps (access/modify/change), block count — detailed metadata
- B) file content — `ls -l` sirf naam deta hai
- C) file ka MD5 hash — integrity check ke liye
- D) file ka owner history — pichle owners

✅ **Sahi Jawab: A**
> `stat` = detailed file metadata. inode, exact timestamps (nanosecond level), block count. forensics mein — file kab access hua, kab change hua — yeh sab `stat` se milta hai. `ls -l` basic info deta hai.

---

**Q10.** `locate passwd` kaam karne ke liye kya zaroori hai?

- A) root access — `sudo locate passwd`
- B) network connection — online database use hoti hai
- C) `find` package installed hona chahiye
- D) database updated honi chahiye — `sudo updatedb` se

✅ **Sahi Jawab: D**
> `locate` = database-based search. database update nahi hua = nayi files nahi milegi. `sudo updatedb` se database refresh karo — phir `locate` sahi kaam karega.

---

**Q11.** `type cd` ka output kya hoga aur kya matlab hai?

- A) `cd is /usr/bin/cd` — external program hai
- B) `cd is a shell builtin` — shell ke andar built hai — alag executable nahi
- C) `cd is aliased to cd --verbose` — alias hai
- D) `cd: not found` — cd install nahi

✅ **Sahi Jawab: B**
> `cd` shell builtin hai — bash ke andar khud implement hai — alag file nahi. isliye `which cd` sirf path nahi deta. `type` more accurate hai — command ki actual nature batata hai.

---

**Q12.** `find / -size +50M -type f 2>/dev/null` kya dhundh raha hai?

- A) 50 MB se chhoti files — `-` matlab less than
- B) exactly 50 MB ki files
- C) 50 MB se badi regular files — `+` matlab greater than
- D) 50 minutes se zyada purani files — `-size` time bhi accept karta hai

✅ **Sahi Jawab: C**
> `-size +50M` = 50 MB se bada. `+` = greater than, `-` = less than, koi sign = exactly. badi files dhundhna disk space management mein use hota hai.

---

**Q13.** web application penetration testing mein `grep -r "password" /var/www/` kyun run karte hain?

- A) web files mein hard-coded passwords dhundhne ke liye — common developer mistake
- B) web application password change karne ke liye
- C) web server ke firewall password check karne ke liye
- D) `/var/www/` folder ka access password set karne ke liye

✅ **Sahi Jawab: A**
> developers kabhi kabhi credentials hard-code kar dete hain source files mein — laziness ya oversight se. `grep -r "password"` se yeh sensitive information dhundh sakte hain — real-world finding hai yeh.

---

**Q14.** `whereis nmap` aur `which nmap` mein kya fark hai?

- A) koi fark nahi — sirf syntax alag
- B) `whereis` nahi mila toh automatically install karta hai
- C) `which` installed check karta hai, `whereis` path dhundh ta hai
- D) `which` sirf executable path. `whereis` binary + source + man page — sab locations

✅ **Sahi Jawab: D**
> `which nmap` = `/usr/bin/nmap` — sirf executable. `whereis nmap` = `nmap: /usr/bin/nmap /usr/share/man/man1/nmap.1.gz` — binary + documentation locations.

---

**Q15.** `find /home -name "*.txt" -exec grep -l "secret" {} \;` kya karta hai?

- A) `/home` mein `.txt` files banata hai jisme "secret" likhta hai
- B) `/home` mein `.txt` files dhundh ke unme "secret" word dhundh ke — jo files mein "secret" hai unke naam print karo
- C) "secret" word wali files delete karta hai
- D) `.txt` files ki grep count karta hai

✅ **Sahi Jawab: B**
> chain: `find` `.txt` files dhundha → `-exec grep -l "secret"` = har file mein "secret" dhundho aur agar mila toh filename print karo (`-l` flag). kisi bhi folder mein sensitive content wali specific files dhundh lo.

---

## 🎯 Task — Topic 5.11 — Kuch Dhundho

**task naam: "system ko explore karo"**

```bash
# 1. kali ke home mein sab files
find /home/kali -type f

# 2. .conf files dhundho
find /etc -name "*.conf" 2>/dev/null | head -10

# 3. SUID files dhundho
find / -perm -4000 -type f 2>/dev/null

# 4. recently modified files
find /etc -mtime -7 2>/dev/null | head -10

# 5. command paths
which python3
which bash
which curl
whereis python3

# 6. passwd file content search
grep -n "kali" /etc/passwd

# 7. locate use karo
sudo updatedb
locate passwd | head -5

# 8. type check karo
type ls
type cd
type python3

# 9. stat command
stat /etc/passwd

# 10. file dhundh ke content dekho
find /etc -name "hostname" -exec cat {} \;
```

**note karo:**
- SUID files kaun si mili?
- `/etc/passwd` mein `kali` user ki entry kya hai?
- `bash` kahan installed hai?

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.11 COMPLETE — FILE SEARCH
   ⬇️  Neeche hai Topic 5.12
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 5.12 — Bash Scripting Basics — Terminal Ko Automatic Karo

---

### ek baar likhao — hazaron baar karo

hacker ka ek rule hai —

> **koi bhi kaam agar do baar se zyada karna pad raha hai — automate karo.**

ek command manually type karna — 1 second.
1000 commands ek ek manually type karna — boring, slow, error prone.
wahi 1000 commands ek script mein — ek button dabao — sab automatic.

**yahi Bash Scripting ka purpose hai.**

---

### Script Kya Hoti Hai?

ek text file jisme commands hote hain — ek ke baad ek — Linux unhe automatically execute karta hai.

```bash
#!/bin/bash
echo "Hello, Kali!"
echo "Aaj ka system info:"
uname -a
whoami
```

save karo — `myscript.sh`
run karo — sab commands ek ke baad ek chalein.

---

### `#!/bin/bash` — Shebang

pehli line hoti hai:
```bash
#!/bin/bash
```

ise **shebang** kehte hain.

matlab: "yeh script bash shell se run karo."

`/bin/bash` = bash ka path. yeh pehli line hona zaroori hai — warna system nahi jaanta kaun si language mein script hai.

---

### Pehli Script Banana aur Chalana

```bash
nano hello.sh
```

likho:
```bash
#!/bin/bash
echo "Meri pehli Bash script!"
echo "Yeh Kali Linux pe chal rahi hai."
date
```

save karo (Ctrl+O, Enter, Ctrl+X).

execute permission do:
```bash
chmod +x hello.sh
```

chalao:
```bash
./hello.sh
```

output:
```
Meri pehli Bash script!
Yeh Kali Linux pe chal rahi hai.
Mon Jan 15 10:30:00 UTC 2024
```

---

### Variables — Data Store Karo

```bash
#!/bin/bash
naam="Afsar"
umar=25
echo "Mera naam $naam hai"
echo "Meri umar $umar saal hai"
```

**rules:**
- variable = `naam=value` (koi space nahi `=` ke aas paas)
- use karte waqt `$naam` — `$` symbol lagao aage
- string mein spaces ho toh quotes: `naam="Afsar Ali"`

**command output variable mein store karo:**
```bash
my_ip=$(ip a | grep "inet " | grep -v "127.0.0.1" | awk '{print $2}')
echo "Mera IP: $my_ip"
```

`$()` = command substitution — andar command ka output variable mein.

---

### User Input Lena — `read`

```bash
#!/bin/bash
echo "Apna naam likho:"
read user_naam
echo "Hello, $user_naam!"
```

`read` = user se input lena. jo type karo — variable mein store hoga.

---

### Conditions — `if/else`

```bash
#!/bin/bash
age=18

if [ $age -ge 18 ]; then
    echo "Adult hai"
else
    echo "Minor hai"
fi
```

**comparison operators:**

| Operator | Matlab |
|---|---|
| `-eq` | equal to |
| `-ne` | not equal to |
| `-gt` | greater than |
| `-lt` | less than |
| `-ge` | greater than or equal |
| `-le` | less than or equal |

**strings ke liye:**
```bash
if [ "$naam" == "kali" ]; then
    echo "Kali user hai"
fi
```

**file check:**
```bash
if [ -f "/etc/passwd" ]; then
    echo "File exist karti hai"
fi
```
`-f` = file exist hai. `-d` = directory exist hai. `-e` = exist hai (file ya directory).

---

### Loops — Repeat Karo

**`for` loop:**
```bash
#!/bin/bash
for i in 1 2 3 4 5; do
    echo "Number: $i"
done
```

output:
```
Number: 1
Number: 2
...
Number: 5
```

**range ke saath:**
```bash
for i in {1..10}; do
    echo "Count: $i"
done
```

**files pe loop:**
```bash
for file in /etc/*.conf; do
    echo "Config file: $file"
done
```

**`while` loop:**
```bash
#!/bin/bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count + 1))
done
```

---

### Functions — Reusable Code

```bash
#!/bin/bash

greet() {
    echo "Hello, $1!"
    echo "Kali Linux pe aapka swagat hai."
}

greet "Afsar"
greet "Hacker"
```

`$1` = function ka pehla argument.

output:
```
Hello, Afsar!
Kali Linux pe aapka swagat hai.
Hello, Hacker!
Kali Linux pe aapka swagat hai.
```

---

### Arguments — Script Ko Input Do

```bash
#!/bin/bash
echo "Script naam: $0"
echo "Pehla argument: $1"
echo "Doosra argument: $2"
echo "Total arguments: $#"
```

chalao:
```bash
./script.sh hello world
```

output:
```
Script naam: ./script.sh
Pehla argument: hello
Doosra argument: world
Total arguments: 2
```

---

### Exit Codes — Success ya Failure?

har command ek **exit code** return karta hai:
- `0` = success
- non-zero = failure (different codes = different errors)

```bash
ls /nonexistent
echo $?
```
`$?` = pichle command ka exit code. `2` aayega — `ls` failed.

```bash
ls /etc
echo $?
```
`0` aayega — success.

**script mein use:**
```bash
#!/bin/bash
ping -c 1 google.com > /dev/null 2>&1

if [ $? -eq 0 ]; then
    echo "Internet connected hai"
else
    echo "Internet nahi hai"
fi
```

---

### Ek Real Script — System Info

```bash
#!/bin/bash

echo "============================================"
echo "      SYSTEM INFORMATION REPORT"
echo "============================================"
echo ""
echo "[*] Hostname:    $(hostname)"
echo "[*] User:        $(whoami)"
echo "[*] Date:        $(date)"
echo "[*] Uptime:      $(uptime -p)"
echo "[*] OS:          $(lsb_release -d | cut -f2)"
echo "[*] Kernel:      $(uname -r)"
echo ""
echo "[*] IP Address:"
ip a | grep "inet " | grep -v "127.0.0.1" | awk '{print "    " $2}'
echo ""
echo "[*] RAM:"
free -h | grep "Mem:" | awk '{print "    Total: " $2 "  Used: " $3 "  Free: " $4}'
echo ""
echo "[*] Disk:"
df -h / | tail -1 | awk '{print "    Total: " $2 "  Used: " $3 "  Free: " $4}'
echo "============================================"
```

yeh script banao — chalao — dekho kya dikhta hai.

---

### Script Debugging

kuch kaam nahi kar raha — debug karo:

```bash
bash -x script.sh
```

`-x` = trace mode — har command print hogi phir execute hogi. exactly samajh aayega kahan fail ho raha hai.

---

### ek line mein

> **Bash script = commands ki list ek file mein. Variables, conditions, loops, functions — in sab se powerful automation scripts banti hain. `chmod +x` do — `./script.sh` se chalao.**

---

## 🧠 MCQ Set — Topic 5.12

---

**Q1.** Bash script ki pehli line `#!/bin/bash` kyun likhte hain?

- A) copyright notice — Bash Foundation ka license
- B) import statement — bash library load karta hai
- C) comment — ignored hota hai, sirf documentation ke liye
- D) shebang — system ko batata hai yeh script kis interpreter se chalao

✅ **Sahi Jawab: D**
> `#!` = shebang. `/bin/bash` = interpreter path. system execute karta hai toh pehle shebang padha — "bash se chalao yeh script." bina iske system nahi jaanta konsa interpreter use kare.

---

**Q2.** variable assign karte waqt `naam = "Afsar"` aur `naam="Afsar"` mein kya fark hai?

- A) koi fark nahi — dono same hain
- B) spaces ke saath string store hoti hai — bina spaces ke integer store hota hai
- C) spaces ke saath `naam = "Afsar"` error dega — Bash mein assignment mein spaces nahi honge
- D) pehla global variable, doosra local variable

✅ **Sahi Jawab: C**
> Bash mein `=` ke aas paas koi space nahi hona chahiye. `naam = "Afsar"` = Bash `naam` ko command samjhega aur `=` aur `"Afsar"` arguments — error aayega. `naam="Afsar"` = correct.

---

**Q3.** `$()` syntax kya karta hai?

- A) subshell mein command chalata hai — output capture karta hai — variable mein store hota hai
- B) special characters escape karta hai
- C) array define karta hai
- D) command ko background mein chalata hai

✅ **Sahi Jawab: A**
> `$(command)` = command substitution. andar command chalti hai — output capture hota hai. `my_date=$(date)` — `date` command ka output `my_date` mein store. `echo $my_date` = date print hogi.

---

**Q4.** Bash mein `-eq` kab use karte hain?

- A) integers compare karne ke liye — numeric equality check
- B) strings compare karne ke liye — "equal" strings
- C) file existence check ke liye
- D) regex pattern match ke liye

✅ **Sahi Jawab: A**
> `-eq` = numeric/integer comparison. strings ke liye `==` use karo (`[ "$str1" == "$str2" ]`). galat comparison = unexpected results. `[ 10 -eq 10 ]` = true. `[ "abc" == "abc" ]` = true.

---

**Q5.** `$#` Bash mein kya represent karta hai?

- A) script ki total line count
- B) last command ka exit code
- C) current process ID (PID)
- D) script ko pass kiye gaye total arguments ki count

✅ **Sahi Jawab: D**
> `$#` = number of arguments. `$0` = script naam. `$1` = pehla arg. `$2` = doosra. `$@` = sare arguments. `./script.sh a b c` → `$# = 3`.

---

**Q6.** `for file in /etc/*.conf; do` loop kya karta hai?

- A) `/etc/` mein sari `.conf` files dhundh ke ek ek pe loop chalata hai
- B) ek file banata hai `/etc/conf` naam se
- C) `.conf` files count karta hai aur count se loop chalata hai
- D) `/etc/` mein sirf ek file read karta hai — `*.conf` = any one match

✅ **Sahi Jawab: A**
> Bash mein `*` wildcard hai — `*.conf` = sari `.conf` files. `for file in /etc/*.conf` = har `.conf` file ke liye variable `file` mein woh path aayega — loop body chalegi.

---

**Q7.** `$?` kya hota hai?

- A) current user ka password
- B) script ka pehla argument
- C) last executed command ka exit code — 0 = success, non-zero = failure
- D) current directory ka path

✅ **Sahi Jawab: C**
> `$?` = exit status of last command. success = 0. failure = 1, 2, 127 (command not found), etc. `if [ $? -eq 0 ]` = agar pichli command successful thi. error handling ke liye essential.

---

**Q8.** `[ -f "/etc/passwd" ]` check kya karta hai?

- A) `/etc/passwd` ka content `f` character se shuru hota hai
- B) `/etc/passwd` empty file hai — `-f` = empty
- C) `/etc/passwd` sirf root ke liye accessible hai
- D) `/etc/passwd` ek regular file hai — exist karti hai

✅ **Sahi Jawab: D**
> `-f` = file exist karta hai aur regular file hai (directory nahi). `-d` = directory. `-e` = exist karta hai (kuch bhi). condition mein file check karne ka standard way.

---

**Q9.** function call karte waqt `greet "Afsar"` mein function ke andar `"Afsar"` kaise milega?

- A) `$1` — pehla positional argument
- B) `$name` — parameter naam automatically set hota hai
- C) `$input` — default input variable naam
- D) `$arg` — function argument variable

✅ **Sahi Jawab: A**
> functions mein bhi `$1`, `$2` etc. use hote hain — scripts ki tarah. `greet "Afsar"` call kiya — function ke andar `$1 = "Afsar"`. multiple arguments ke liye `$2`, `$3` etc.

---

**Q10.** `bash -x script.sh` kyun use karte hain?

- A) script ko X11 (GUI) mode mein chalate hain
- B) script ko extra permissions de ke chalate hain
- C) debug mode — har command print hoti hai execute hone se pehle — troubleshoot karne ke liye
- D) external mode — internet se script fetch karke chalate hain

✅ **Sahi Jawab: C**
> `-x` = xtrace = debug. har command `+` ke saath print hogi phir execute hogi. kahan script fail ho rahi hai — exactly dikhayi dega. script kaam nahi kar raha? `bash -x` se debug karo.

---

**Q11.** `count=$((count + 1))` syntax kya hai?

- A) `$()` command substitution — `count + 1` command hai
- B) array indexing — count ka index 1 pe value
- C) string concatenation — "count" aur "1" join karo
- D) `$(( ))` arithmetic expansion — integers ke calculations ke liye

✅ **Sahi Jawab: D**
> `$(( ))` = arithmetic expansion. andar math operations karo. `$((5 + 3))` = 8. `$((count + 1))` = count mein 1 add karo. Bash mein integers ke liye yahi use karo.

---

**Q12.** `while [ $count -le 5 ]` loop kab rok jaata hai?

- A) jab `count` 5 se equal ho jaaye
- B) jab `count` 5 se zyada ho jaaye — `-le` = less than or equal to, condition false hone pe rukta hai
- C) exactly 5 iterations ke baad — count value irrelevant
- D) manually `Ctrl + C` se hi rukta hai — infinite loop hai

✅ **Sahi Jawab: C**
> `-le` = less than or equal. loop tab tak chalta hai jab condition true ho. `count = 6` hone pe `6 -le 5` = false — loop ruk jaata hai. `count` ko loop ke andar increment karna zaroori hai — warna infinite loop.

---

**Q13.** script ko run karne ke liye pehle kya karna padta hai?

- A) `sudo script.sh` — root se run karo
- B) `source script.sh` — source command se run karo
- C) `chmod +x script.sh` — execute permission do — phir `./script.sh`
- D) `.sh` extension automatically executable banata hai — kuch extra nahi

✅ **Sahi Jawab: C**
> `.sh` extension sirf convention hai — automatically executable nahi. `chmod +x` se execute bit set karo. phir `./script.sh`. ya `bash script.sh` bhi kaam karta hai — permission ki zarurat nahi.

---

**Q14.** `read user_input` ka kaam kya hai?

- A) ek file read karta hai named `user_input`
- B) user se keyboard input leta hai aur `user_input` variable mein store karta hai
- C) environment variable read karta hai
- D) last command ka output `user_input` mein store karta hai

✅ **Sahi Jawab: B**
> `read variable_naam` = stdin se ek line leti hai (keyboard) — variable mein store. interactive scripts ke liye essential. `read -p "IP enter karo: " target_ip` — prompt ke saath bhi use karte hain.

---

**Q15.** ek script likhni hai jo check kare Google reachable hai ya nahi — sahi approach kya hai?

- A) browser script — curl use karo aur output manually check karo
- B) `ping -c 1 google.com > /dev/null 2>&1` chalao — `$?` check karo — 0 toh connected, nahi toh offline
- C) `/etc/resolv.conf` mein Google ka IP hardcode karo
- D) `google_status=$(host google.com)` — agar empty toh offline

✅ **Sahi Jawab: B**
> `ping -c 1 > /dev/null 2>&1` — sirf check karo — output suppress. `if [ $? -eq 0 ]` — 0 = success = connected. reliable internet check ka standard pattern Bash scripts mein.

---

## 🎯 Task — Topic 5.12 — Apni Script Banao

**task naam: "pehli useful script"**

**Script 1 — Hello Script (Warm Up):**

```bash
nano ~/my_scripts/hello.sh
```

```bash
#!/bin/bash
echo "Hello, $(whoami)!"
echo "Aaj ka din: $(date '+%A, %d %B %Y')"
echo "Kali Linux version: $(lsb_release -d | cut -f2)"
```

```bash
chmod +x ~/my_scripts/hello.sh
./hello.sh
```

---

**Script 2 — System Check Script:**

```bash
nano ~/my_scripts/syscheck.sh
```

```bash
#!/bin/bash

echo "=========================================="
echo "         KALI SYSTEM CHECK"
echo "=========================================="

# Internet check
echo -n "[*] Internet: "
ping -c 1 8.8.8.8 > /dev/null 2>&1
if [ $? -eq 0 ]; then
    echo "Connected ✓"
else
    echo "Offline ✗"
fi

# User check
echo "[*] Current User: $(whoami)"

# IP
echo "[*] IP Address: $(ip a | grep 'inet ' | grep -v '127' | awk '{print $2}' | head -1)"

# RAM
echo "[*] RAM Free: $(free -h | grep Mem | awk '{print $4}')"

# Disk
echo "[*] Disk Free: $(df -h / | tail -1 | awk '{print $4}')"

echo "=========================================="
```

```bash
chmod +x ~/my_scripts/syscheck.sh
./my_scripts/syscheck.sh
```

---

**Script 3 — Loop Practice:**

```bash
nano ~/my_scripts/pingcheck.sh
```

```bash
#!/bin/bash

echo "Common hosts check:"
hosts=("8.8.8.8" "8.8.4.4" "1.1.1.1")

for host in "${hosts[@]}"; do
    echo -n "Pinging $host... "
    ping -c 1 $host > /dev/null 2>&1
    if [ $? -eq 0 ]; then
        echo "UP ✓"
    else
        echo "DOWN ✗"
    fi
done
```

```bash
chmod +x ~/my_scripts/pingcheck.sh
./my_scripts/pingcheck.sh
```

```
════════════════════════════════════════════════════════
   ✅  TOPIC 5.12 COMPLETE — BASH SCRIPTING
   🎉  CHAPTER 5 COMPLETE — KALI LINUX
════════════════════════════════════════════════════════
```

---
---

## 🏁 Chapter 5 — Complete Summary

is chapter mein tumne yeh sab seekha:

| Topic | Kya Seekha |
|---|---|
| **5.1** | Kali Linux ki history, Offensive Security, rolling release |
| **5.2** | VM, Live Boot, Dual Boot, WSL2 — installation methods |
| **5.3** | VirtualBox pe Kali install — step by step |
| **5.4** | XFCE desktop, terminal shortcuts, workspaces |
| **5.5** | Navigation — pwd, ls, cd, mkdir, rm, cp, mv |
| **5.6** | Files — cat, less, head, tail, nano, grep, echo |
| **5.7** | Users, permissions, chmod, chown, sudo |
| **5.8** | Networking — ip, ping, netstat, ss, curl, wget |
| **5.9** | Piping, redirection — \|, >, >>, grep, sort, uniq |
| **5.10** | Processes — ps, top, htop, kill, jobs, bg, fg |
| **5.11** | Search — find, locate, which, whereis, grep -r |
| **5.12** | Bash scripting — variables, conditions, loops, functions |

---

### ab tum kya kar sakte ho?

- Kali Linux VM install aur manage kar sakte ho
- File system mein navigate kar sakte ho — aankhein band karke
- Files banao, dekho, edit karo, delete karo
- Users aur permissions samajhte aur set kar sakte ho
- Network information nikaal sakte ho terminal se
- Commands ko chain karo — powerful pipelines banao
- Processes dekhte aur manage kar sakte ho
- Kuch bhi dhundh sakte ho system mein
- Basic automation scripts likh sakte ho

> **Kali Linux ab tumhare liye ek nayi jagah nahi hai — tumhara ghar hai.**
> **Agle chapters mein in foundations ke upar actual security tools sikhenge.**

---
