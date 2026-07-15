# Chapter 8 — Famous Hacking Techniques Aur Tools
### By TWH (Afsar Ali) | Technical White Hat

---

## 📚 Table of Contents

| # | Topic | Jump |
|---|---|---|
| 8.1 | Phishing Technique Aur Zphisher Tool — Termux + Kali | [➜ Jao](#-topic-81--phishing-technique-aur-zphisher-tool--termux--kali) |

---
---

**badhai ho guys** — Chapter 1 se lekar Chapter 7 tak jo bhi seekha — computer, networking, Linux, Kali, Termux, aur tool/programming language ka concept — woh saari **taiyaari** thi. asli maza ab shuru hota hai.

is chapter mein hum har topic mein **ek famous real-world hacking technique** lenge, usko poori tarah samjhenge (kaam kaise karti hai, kyun kaam karti hai), aur uske saath jo **actual tool** use hota hai — usko **Termux aur Kali Linux dono mein install** karna aur **use karna** seekhenge.

pehla topic — sabse common aur sabse zyada real-life mein hone wala attack — **Phishing.**

⚠️ **ek zaroori baat shuru mein hi clear kar dete hain:** yeh chapter tumhe yeh tool **sirf seekhne aur samajhne ke liye** dikha raha hai — taaki tum jaan sako yeh attack kaise hota hai aur **khud ko/logo ko bacha sako.** kisi bhi real insaan pe, uski permission ke bina, yeh tool use karna **illegal** hai. is course mein hum sirf apne khud ke test account/apne banaye demo pe practice karenge.

chalo, welcome karte hain **Chapter 8** mein.

---
---

## 📌 Topic 8.1 — Phishing Technique Aur Zphisher Tool — Termux + Kali

---

### Phishing kya hota hai — seedhi baat

> **Phishing ek aisi technique hai jisme hacker ek asli website (jaise Facebook, Instagram, Gmail) ki nakli (fake) copy banata hai, aur victim ko woh nakli link bhejta hai. victim jab us fake page pe apna email/password daalta hai, woh details seedha hacker ke paas chali jaati hain — asli website pe kuch hota hi nahi.**

yeh naam "**fishing**" (machli pakadna) se aaya hai — jaise machhli pakadne wala ek chaara (bait) daalta hai aur machhli khud aakar phas jaati hai, waise hi hacker ek "chaara" (fake login page ka link) daalta hai aur victim khud apni details de deta hai.

---

### phishing itni famous/dangerous kyun hai

kyunki isme **koi technical hacking nahi hoti** — na password crack karna padta hai, na system mein ghusna padta hai. hacker sirf ek **insaan ko dhoka** deta hai (ise "**Social Engineering**" kehte hain — insaan ki galti/vishwaas ka fayda uthana). isiliye duniya mein sabse zyada hacking cases **phishing se hi shuru hote hain** — bade se bade company hack bhi kabhi kabhi ek employee ke phishing email pe click karne se shuru hue hain.

---

### ek real-life example se samjho

socho tumhe ek message aata hai: *"tumhara Instagram account 24 ghante mein delete ho jaayega, abhi login karke confirm karo"* — saath mein ek link hai. woh link dikhta hai bilkul Instagram jaisa (logo, colors, layout sab same), lekin **URL** dhyaan se dekho toh woh Instagram.com nahi hota — kuch alag hota hai.

agar koi jaldi mein, bina URL check kiye, apna username-password daal de — woh details seedha attacker ke paas chali jaati hain, aur asli Instagram pe kabhi kuch hua hi nahi.

**yehi hai phishing — nakli page, asli jaisi dikhne wali cheez, aur ek jaldi mein liya gaya galat decision.**

---

### iske liye tool ka naam hai — Zphisher

ab is technique ko practically samajhne ke liye (sirf apne demo pe, khud pe test karne ke liye) hum ek famous open-source tool use karenge jiska naam hai — **Zphisher**.

> Zphisher ek **automated phishing tool** hai jo popular websites (Facebook, Instagram, Google, etc.) ke **ready-made fake login pages** already bana ke rakhta hai — tumhe khud page design nahi karna padta, tool khud sab kar deta hai.

yeh tool **Bash script** mein likha gaya hai (Topic 7.2 yaad hai? — yehi wajah hai ki yeh Termux aur Kali dono mein bina kisi jhanjhat ke chal jaata hai, kyunki dono jagah Bash already available hai).

---

### Zphisher install karna — Termux mein

Termux khol lo, aur yeh commands step-by-step chalao:

```bash
pkg install tur-repo
pkg install zphisher
```

- pehli command — `tur-repo` naam ka ek extra repository (Topic 6.6 yaad karo — repository matlab jahan se packages milte hain) add karti hai, kyunki Zphisher normal Termux repo mein nahi hota.
- doosri command — usi repo se `zphisher` package install kar deti hai.

install hone ke baad, tool chalane ke liye sirf yeh likho:

```bash
zphisher
```

---

### Zphisher install karna — Kali Linux mein

Kali Linux (ya kisi bhi normal Linux) mein install karne ka tarika thoda alag hai — yahan hum tool ko **GitHub se clone** karte hain (matlab uska code seedha download karna):

```bash
git clone --depth=1 https://github.com/htr-tech/zphisher.git
cd zphisher
bash zphisher.sh
```

- pehli command — Zphisher ka poora code GitHub se tumhare Kali mein copy kar leti hai.
- doosri command — usi folder ke andar jaati hai jo clone hua.
- teesri command — tool ko chalati hai. **pehli baar chalate waqt** yeh khud-ba-khud zaroori dependencies (`git`, `curl`, `php`) install kar lega.

---

### Zphisher use kaise karna hai — step by step

install hone ke baad, jab tum `zphisher` (Termux) ya `bash zphisher.sh` (Kali) chalaoge, ek **menu screen** khulegi:

1. **website choose karo** — menu mein numbers ke saath list dikhegi (jaise 1 = Instagram, 2 = Facebook, 3 = Google, etc.). jis website ka fake page banana hai, uska number type karo.
2. **login page ka type choose karo** — kuch websites ke liye multiple page-styles milte hain (jaise "Instagram — normal login" ya "Instagram — followers dekhne wala trick"). koi ek number choose karo.
3. **tunneling option choose karo** — yeh sabse important step hai. tumhara fake page abhi tumhare hi phone/laptop pe chal raha hai (localhost pe) — usko **internet pe kisi aur ko bhejne wala link** banane ke liye "tunnel" chahiye. options milte hain jaise:
   - **Localhost** — sirf tumhare khud ke device/network tak kaam karega (demo/testing ke liye best)
   - **Cloudflared** — ek public link banata hai jo kahin se bhi khul sakta hai
4. tool ek **link generate karega** — yehi woh link hai jo phishing message mein bheja jaata hai.
5. jab koi (tumhara khud ka test account) us link ko khol ke apna username/password daalega — woh details **turant tumhari terminal screen pe** dikh jaayengi.

---

### zaroori disclaimer — dobara, kyunki yeh critical hai

> **is tool ka use sirf apne khud ke banaye demo account pe, apne khud ke device pe, ya kisi ki likhi hui permission ke saath hi karna hai.** kisi bhi real insaan ko, uski jaankari/permission ke bina, fake link bhejna **cyber crime** hai — chahe woh "sirf mazak" ke liye ho. is course ka maksad hai tumhe yeh sikhana ki **attack kaise hota hai, taaki tum khud ko aur doosron ko bacha sako** — attack karna nahi.

---

### ek line mein

> **Phishing ek fake login page bana ke, victim ko dhoka dekar uske username/password churane ki technique hai — bina koi technical hacking kiye, sirf insaan ke vishwaas ka fayda uthaya jaata hai. Zphisher ek Bash-based tool hai jo yeh fake pages ready-made deta hai — Termux mein `pkg install zphisher` se aur Kali mein GitHub clone karke install hota hai — hamesha sirf apni permission wale demo pe use karna hai.**

---

## 🧠 MCQ Set — Topic 8.1

---

**Q1.** Phishing technique mein hacker asal mein kya karta hai?

- A) victim ke phone ka password directly crack karta hai
- B) ek asli website ki nakli copy (fake login page) banata hai aur victim ko dhoka dekar uski details le leta hai
- C) victim ke phone ka hardware kharab karta hai
- D) internet ki speed slow kar deta hai

✅ **Sahi Jawab: B**
> phishing mein koi technical hacking nahi hoti — sirf ek fake page banake insaan ko dhoka diya jaata hai.

---

**Q2.** phishing ko "Social Engineering" ka example kyun kaha jaata hai?

- A) kyunki ismein computer hardware use hota hai
- B) kyunki ismein internet ka use nahi hota
- C) kyunki ismein technical hacking ke bajaye insaan ke vishwaas/galti ka fayda uthaya jaata hai
- D) kyunki yeh sirf social media companies use karti hain

✅ **Sahi Jawab: C**
> Social Engineering matlab insaan ko manipulate karke kaam nikalna — phishing isi ka ek example hai.

---

**Q3.** Zphisher tool basically kya karta hai?

- A) victim ke phone ka data delete karta hai
- B) popular websites ke ready-made fake login pages provide karta hai, jinka link victim ko bheja jaata hai
- C) sirf internet speed test karta hai
- D) sirf photos edit karta hai

✅ **Sahi Jawab: B**
> Zphisher automated tool hai jo already-bane fake login pages deta hai, taaki manually design na karna pade.

---

**Q4.** Zphisher Termux mein kaise install hota hai?

- A) `pkg install tur-repo` phir `pkg install zphisher`
- B) `pkg install nano`
- C) GitHub clone karke, Termux mein clone hi nahi hota
- D) Play Store se download karke

✅ **Sahi Jawab: A**
> Zphisher normal Termux repo mein nahi hota, isliye pehle `tur-repo` add karke phir `zphisher` install karte hain.

---

**Q5.** Kali Linux mein Zphisher install karne ka tarika kya hai?

- A) `pkg install zphisher`
- B) GitHub se `git clone` karke, folder ke andar jaakar `bash zphisher.sh` chalana
- C) sirf `apt install zphisher` se
- D) Kali mein yeh tool chal hi nahi sakta

✅ **Sahi Jawab: B**
> Kali mein Zphisher GitHub se clone karke, uski script (`zphisher.sh`) directly run karke install/chalaya jaata hai.

---

**Q6.** Zphisher chalane ke baad "tunneling option" (jaise Localhost ya Cloudflared) kis kaam ke liye poochta hai?

- A) sirf tool ka color theme choose karne ke liye
- B) fake page ka link generate karne ke liye — taaki woh link kahin se khola ja sake
- C) phone ki battery bachane ke liye
- D) tool delete karne ke liye

✅ **Sahi Jawab: B**
> tunneling option decide karta hai fake page kis tarah accessible hoga — sirf local network mein (Localhost) ya kahin se bhi (Cloudflared).

---

**Q7.** jab victim fake page pe apna username/password daal deta hai, toh woh details kahan jaati hain?

- A) asli website (jaise real Instagram) ke server pe
- B) seedha attacker ki terminal screen pe dikh jaati hain
- C) kahin nahi jaati, delete ho jaati hain
- D) sirf victim ke apne phone mein save hoti hain

✅ **Sahi Jawab: B**
> Zphisher chalane wale ki terminal pe hi entered credentials turant dikh jaate hain, asli website ka koi role nahi hota.

---

**Q8.** is topic mein bataye gaye rule ke hisaab se, Zphisher jaisa tool kab use karna sahi hai?

- A) kisi bhi random insaan pe, bina bataye, "mazak" ke liye
- B) sirf apne khud ke test account/device pe, ya jiski likhi permission ho, seekhne ke maksad se
- C) sirf apne dost ke account pe uske bina bataye
- D) kabhi bhi, kahin bhi, kisi pe bhi

✅ **Sahi Jawab: B**
> permission ke bina kisi real insaan pe use karna cyber crime hai — is course ka maksad hai defend karna seekhna, attack karna nahi.

---

```
════════════════════════════════════════════════════════
   ✅  TOPIC 8.1 COMPLETE — PHISHING AUR ZPHISHER
   ⬇️  Agla Topic Aane Wala Hai
════════════════════════════════════════════════════════
```

---
