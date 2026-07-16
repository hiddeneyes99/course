# Chapter 8 — Famous Hacking Techniques Aur Tools
### By TWH (Afsar Ali) | Technical White Hat

---

## 📚 Table of Contents

| # | Topic | Jump |
|---|---|---|
| 8.1 | Phishing | [➜ Jao](#-topic-81--phishing-technique-aur-zphisher-tool--termux--kali) |
| 8.2 | Brute Force | [➜ Jao](#-topic-82--brute-force) |

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

sabse pehle, `git` install karna padega — kyunki isi ke through hum GitHub se Zphisher ka code copy (clone) karenge:

```bash
pkg install git
```

`git` install hone ke baad, yeh commands step-by-step chalao:

```bash
git clone --depth=1 https://github.com/htr-tech/zphisher.git
cd zphisher
bash zphisher.sh
```

- pehli command (`pkg install git`) — `git` naam ka tool install karti hai, jiske bina GitHub se code clone nahi kar sakte.
- doosri command (`git clone ...`) — Zphisher ka poora code GitHub se tumhare Termux mein copy kar leti hai.
- teesri command (`cd zphisher`) — usi folder ke andar jaati hai jo clone hua.
- chauthi command (`bash zphisher.sh`) — tool ko chalati hai. **pehli baar chalate waqt** yeh khud-ba-khud zaroori dependencies (`curl`, `php`) install kar lega.

yahan dekho — `bash zphisher.sh` chalane ke baad terminal kuch aisa dikhta hai:

![Zphisher command in terminal](assets/chapter-8-famous-hacking-tools/8.1-01-cmd.png)

aur pehli baar chalane pe yeh khud-ba-khud packages install karna shuru kar deta hai:

![Zphisher installing packages](assets/chapter-8-famous-hacking-tools/8.1-02-installing.png)

---

### Zphisher install karna — Kali Linux mein

Kali Linux mein bhi bilkul wahi tarika follow karenge — pehle check/install `git`, phir GitHub se clone:

```bash
sudo apt install git
```

(zyada tar Kali Linux mein `git` **already pre-installed** aata hai, lekin upar wali command chala kar confirm/install kar lo — agar already hoga toh yeh "already the newest version" bol dega.)

uske baad wahi commands:

```bash
git clone --depth=1 https://github.com/htr-tech/zphisher.git
cd zphisher
bash zphisher.sh
```

- pehli command — Zphisher ka poora code GitHub se tumhare Kali mein copy kar leti hai.
- doosri command — usi folder ke andar jaati hai jo clone hua.
- teesri command — tool ko chalati hai. **pehli baar chalate waqt** yeh khud-ba-khud zaroori dependencies (`curl`, `php`) install kar lega.

> **dhyaan do** — Termux aur Kali dono mein install karne ka tarika ab **bilkul same** hai — `git install karo → git clone karo → cd zphisher → bash zphisher.sh`. bas pehli command (git install karne ka tarika) alag hai (`pkg install git` vs `sudo apt install git`), baaki sab identical hai.

---

### Zphisher use kaise karna hai — step by step

install hone ke baad, jab tum `zphisher` (Termux) ya `bash zphisher.sh` (Kali) chalaoge, ek **menu screen** khulegi:

**Step 1 — website choose karo**

menu mein numbers ke saath list dikhegi — Facebook, Instagram, Google se lekar 34 platforms tak. jis website ka fake page banana hai, uska number type karo.

![Zphisher main menu with 34 platforms](assets/chapter-8-famous-hacking-tools/8.1-03-main-menu.png)

**Step 2 — login page ka type choose karo**

kuch websites ke liye multiple page-styles milte hain. jaise Facebook choose kiya toh yeh options aate hain:

![Facebook page type options](assets/chapter-8-famous-hacking-tools/8.1-04-page-types.png)

**Step 3 — tunneling option choose karo**

yeh sabse important step hai. tumhara fake page abhi tumhare hi phone/laptop pe chal raha hai (localhost pe) — usko accessible banane ke liye tunneling option choose karna padta hai:

![Port forwarding options: Localhost, Ngrok, Cloudflared, LocalXpose](assets/chapter-8-famous-hacking-tools/8.1-05-port-forward.png)

   - **[01] Localhost** — sirf tumhare khud ke device pe kaam karega (demo/testing ke liye best — koi bahar nahi jaata)
   - **[02] Ngrok.io** — public link banata hai, lekin account chahiye
   - **[03] Cloudflared** — public link banata hai, auto detect karta hai
   - **[04] LocalXpose** — naya option, max 15 min ka link deta hai

Localhost choose karne ke baad yeh custom port ke baare mein poochta hai — bas **N** press karo (default port theek hai):

![Custom port question after selecting Localhost](assets/chapter-8-famous-hacking-tools/8.1-06-localhost.png)

**Step 4 — link generate hoga**

sab set hone ke baad terminal kuch aisa dikhta hai — tool hosted ho jaata hai aur login info ka wait karta hai:

![Successfully hosted, waiting for login info](assets/chapter-8-famous-hacking-tools/8.1-07-hosted.png)

**Step 5 — victim ka page kholna aur credentials capture hona**

ab jo link generate hua woh browser mein kholo — aisa dikhega:

![Fake Facebook login page](assets/chapter-8-famous-hacking-tools/8.1-08-fake-page.png)

> dhyaan se dekho upar — browser ke **address bar** mein `127.0.0.1:8080/mobile` likha hai — `facebook.com` nahi. page ke andar bilkul asli Facebook jaisa dikhta hai — logo, colors, fields sab same. **yahi phishing ka poora kaam hai** — bahar se pakadna mushkil, andar se ek dum khali.

ab us page pe koi bhi details daalo (test ke liye sirf fake details — jaise `demo` aur `Pass@123`):

![Credentials type hote hue](assets/chapter-8-famous-hacking-tools/8.1-09-creds-entered.png)

**Log In** button dabate hi — woh details seedha terminal pe aa jaati hain:

![Terminal pe captured credentials](assets/chapter-8-famous-hacking-tools/8.1-10-captured.png)

> terminal mein dekho — `[-] Login info Found !!` aaya, phir neeche `Account : demo` aur `Password : Pass@123` clearly dikh raha hai. victim ne abhi abhi apna password diya — aur usse pata bhi nahi chala. asli Facebook pe kuch hua hi nahi.

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

- A) sirf `pkg install zphisher` se, seedha
- B) pehle `pkg install git` se git install karo, phir `git clone` se code download karke `bash zphisher.sh` chalao
- C) Play Store se download karke
- D) Termux mein yeh tool chal hi nahi sakta

✅ **Sahi Jawab: B**
> Termux mein pehle `git` install karna padta hai, uske baad GitHub se `git clone` karke, folder ke andar jaakar `bash zphisher.sh` se chalate hain.

---

**Q5.** Kali Linux mein Zphisher install karne ka tarika, Termux ke tarike se kaisa hai?

- A) bilkul alag hai, koi similarity nahi
- B) bilkul same hai — git install karo, git clone karo, `cd zphisher`, phir `bash zphisher.sh` — bas git install karne ki command (`pkg` vs `apt`) alag hai
- C) Kali mein sirf `apt install zphisher` se ho jaata hai
- D) Kali mein yeh tool chal hi nahi sakta

✅ **Sahi Jawab: B**
> dono jagah process same hai — git install → git clone → cd zphisher → bash zphisher.sh. sirf git install karne ki command Termux (`pkg`) aur Kali (`apt`) mein alag hai.

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

**Q9.** Zphisher tool kis programming language (script) mein likha gaya hai?

- A) Python
- B) Java
- C) Bash
- D) C++

✅ **Sahi Jawab: C**
> Zphisher ek Bash script hai — isiliye Termux aur Kali dono mein bina extra setup ke chal jaata hai, kyunki dono jagah Bash already available hoti hai.

---

**Q10.** phishing attack mein sabse pehle kaunsi cheez victim ko dhoka dene ka kaam karti hai?

- A) victim ka phone hack ho jaata hai seedha
- B) ek nakli login page jo bilkul asli website jaisi dikhti hai
- C) virus send kiya jaata hai email ke zariye
- D) victim ka internet band kar diya jaata hai

✅ **Sahi Jawab: B**
> phishing ki puri taakat uski visual similarity mein hai — nakli page itna asli dikhta hai ki victim bina sooche apna password daal deta hai.

---

**Q11.** Zphisher mein "Cloudflared" tunneling option ka kya kaam hota hai?

- A) tool ki speed badhata hai
- B) tool uninstall karta hai
- C) ek public link banata hai jo internet pe kahin se bhi access kiya ja sake
- D) sirf local Wi-Fi ke andar kaam karta hai

✅ **Sahi Jawab: C**
> Cloudflared ek public accessible link generate karta hai — taaki fake page sirf tumhare network tak limited na rahe.

---

**Q12.** "phishing" naam kahan se aaya hai?

- A) ek hacker ke naam se
- B) "fishing" (machli pakadna) se — jaise machhliwala chaara daalke machhli phasata hai, hacker fake link se victim ko phasata hai
- C) ek virus ke naam se
- D) "phone hacking" ke short form se

✅ **Sahi Jawab: B**
> naam bilkul fishing se inspired hai — bait (chaara) daalo, victim khud aa ke phas jaaye.

---

**Q13.** agar koi keh raha ho ki "main sirf apne dost ka account test ke liye phish karunga, usse bata bhi dunga baad mein" — yeh sahi hai ya galat?

- A) bilkul sahi — dost hai toh koi baat nahi
- B) galat — permission pehle leni hoti hai, baad mein batana legal nahi hota
- C) sahi — agar baad mein bata do toh crime nahi
- D) sahi — sirf strangers pe use karna galat hota hai

✅ **Sahi Jawab: B**
> permission likhit mein pehle chahiye — "baad mein bataunga" wali baat legally koi value nahi rakhti, yeh crime hi hai.

---

**Q14.** Zphisher use karte waqt website choose karne ke baad kaunsa step aata hai?

- A) seedha link generate ho jaata hai
- B) tool band ho jaata hai
- C) login page ka type/style choose karna padta hai
- D) phone restart karna padta hai

✅ **Sahi Jawab: C**
> website choose karne ke baad, tool poochta hai kaunsa page style chahiye (jaise "normal login" ya koi special variant) — phir tunneling choose hoti hai, phir link generate hota hai.

---

**Q15.** phishing attacks itne common kyun hain — technical hacking ki jagah?

- A) kyunki yeh free hai
- B) kyunki ismein koi coding nahi chahiye aur insaan ki psychology exploit hoti hai — yeh sabse aasaan aur effective attack vector hai
- C) kyunki police track nahi kar sakti
- D) kyunki yeh sirf mobile pe kaam karta hai

✅ **Sahi Jawab: B**
> system hack karna mushkil hota hai — insaan ko dhoka dena zyada aasaan. isiliye duniya ki most hacking incidents phishing se hi shuru hoti hain.

---

## 🛠️ Hands-On Task — Topic 8.1

**Task: Apne Khud Ke Liye Ek Phishing Demo Setup Karo — Aur Khud Hi Usse "Bachna" Seekho**

Yeh task do histon mein hai — pehle attacker ki taraf se dekho (apne test pe), phir defender ki taraf se.

---

**Hissa 1 — Phishing Demo Karo (sirf apne test account pe)**

1. **Termux ya Kali mein Zphisher install karo** — upar wale steps follow karo.
2. Tool chalao: `bash zphisher.sh`
3. Facebook choose karo (option **01**), phir **Traditional Login Page** (option **01**).
4. Tunneling option mein **Localhost** (option **01**) choose karo — link sirf tumhare apne device pe hi kaam karega, koi bahar nahi jaayega. Custom port ke liye **N** press karo.
5. Jo link generate hua (`http://127.0.0.1:8080`), woh apne phone ke browser mein kholo — kuch aisa dikhega:

![Fake Facebook login page in browser](assets/chapter-8-famous-hacking-tools/8.1-08-fake-page.png)

dekho — bilkul asli Facebook jaisa lag raha hai, lekin **URL bar** mein `127.0.0.1:8080` likha hai — facebook.com nahi! Yahi sabse bada clue hai phishing pakadne ka.

6. **Real account bilkul mat use karna** — koi bhi fake details daalo jaise `demo` / `Pass@123`:

![Entering demo credentials on fake page](assets/chapter-8-famous-hacking-tools/8.1-09-creds-entered.png)

7. Ab terminal pe wapas jao — details turant wahan capture ho gayi hain:

![Captured credentials shown in terminal](assets/chapter-8-famous-hacking-tools/8.1-10-captured.png)

> **Yahi phishing hoti hai.** Tumne khud apna ek "attack" dekha — bina koi real account use kiye, bina kisi aur ko involve kiye.

---

**Hissa 2 — Ab Defender Bano (yahi asli lesson hai)**

Woh same fake page kholo jo tune abhi banaya — aur dhyaan se dekho:

1. **URL check karo** — kya woh sach mein instagram.com hai? ya kuch aur hai (jaise 127.0.0.1:8080 ya koi random domain)?
2. **HTTPS lock icon dekho** — kya hai? genuine sites pe hota hai.
3. **Page ka source dekho** — browser mein Ctrl+U — dikhaai dega yeh local file hai ya server se aa raha hai.

**Yeh 3 cheezein real life mein kisi bhi link pe check karo — phishing se kabhi nahi fasoge.**

---

> 💡 **Tip:** Duniya ke 90% phishing attacks tab kaam karte hain jab victim jaldi mein hota hai ya daraya gaya hota hai ("account delete ho jaayega!"). Jab bhi aisa koi message aaye — **ruko, URL dekho, tab decide karo.** Hacker ki sabse badi dushman tumhari **slow, deliberate reaction** hai.

---

## 🎉 Ek Pal Ruko — Tumne Abhi Apni Zindagi Ka Pehla "Hack" Kiya Hai

terminal mein woh line dekhi?

```
[-] Login info Found !!
[-] Account : demo
[-] Password : Pass@123
```

woh tumne kiya. khud apne haath se. pehli baar.

yeh feeling — jab pehli baar koi cheez kaam karti hai jo tumne socha tha sirf movies mein hoti hai — **yeh feeling hamesha yaad rehti hai.** pehla hack hamesha special hota hai. chahe woh sirf ek demo account pe ho, chahe sirf localhost pe — koi farq nahi padta. tumne kiya. aur yahi kaafi hai aaj ke liye.

toh ek second ke liye ruko. mehsoos karo. **badhai ho.**

---

### lekin ek zaroori baat — seedhi aur honest

ab jo main kehne wala hun woh sunna bahut zaroori hai —

> **phishing hacking nahi hai.**

haan, tumne abhi jo kiya — woh ek real attack technique hai, duniya mein sabse zyada hone wali. lekin agar koi tumse pooche "kya tum hacker ho?" — toh sirf is ek cheez ko karke "haan" bolna sahi nahi hoga.

kyun?

kyunki phishing mein tumne **koi system hack nahi kiya.** tumne koi code nahi likha. koi vulnerability nahi dhundhi. koi firewall bypass nahi ki. tumne sirf ek **insaan ko dhoka dene ki technique** dekhi — jo ki ethical hacking ki duniya ka ek bahut chota sa hissa hai.

socho aise — agar hacking ek poori university hai, toh phishing sirf **orientation day** hai. pehla din. class abhi shuru bhi nahi hui.

asli hacking mein hota hai:

- systems ki vulnerabilities dhundhna aur exploit karna
- networks ko samajhna aur unke andar ghusna
- code likhna — exploits, scripts, tools
- forensics — evidence dhundhna ya mitana
- privilege escalation — ek baar andar gaye toh aur andar jaana
- aur bahut kuch — jo aage ke topics mein aayega

---

### toh phir yeh sab kyun seekha?

kyunki **har badi cheez ek chote se shuru hoti hai.**

duniya ke sabse bade hackers ne bhi kabhi pehli baar kuch chota kiya tha — aur us moment ne unhe yaad dilaya ki yeh field kitni powerful hai, kitni interesting hai, aur yahan kitna kuch seekhna baaki hai.

tumhara woh moment abhi tha.

is topic ne tumhe ek cheez di jo books mein nahi milti — **hands-on experience ka pehla zing.** woh curiosity jo ab jagee hai, woh energy jo feel ho rahi hai — **isi ko sambhal ke rakho.** yahi tumhara asli hacking ka fuel hai.

safar abhi shuru hua hai. aage bahut kuch hai. chalo badhte hain. 🚀

---

```
════════════════════════════════════════════════════════
   ✅  TOPIC 8.1 COMPLETE — PHISHING AUR ZPHISHER
   ⬇️  Neeche hai Topic 8.2
════════════════════════════════════════════════════════
```

---
---

## 📌 Topic 8.2 — Brute Force

---

### Brute Force kya hota hai — ek dum seedha

> **Brute Force ek aisi technique hai jisme hacker ek ke baad ek hazaron passwords try karta rehta hai — jab tak sahi password nahi mil jaata. koi "hacking" nahi, koi trick nahi — sirf baar baar alag alag combinations aazmaana, jab tak taala khul na jaaye.**

iska naam sun ke lagta hai — "yeh toh bahut simple aur boring hai, isme skill kahan hai?" — lekin yahi is attack ki asli taqat hai. jab tool machine speed se kaam karta hai — ek second mein **hazaaron ya laakhon passwords** try kar sakta hai — tab "boring" bhi bahut khatarnak ho jaata hai.

---

### real-life analogy — combination lock

socho ek combination lock hai — 0000 se 9999 tak koi bhi 4-digit code ho sakta hai. agar tum manually ek ek number try karo toh 10,000 combinations hain — ghanton lag jaayenge.

lekin ek machine ko do yahi kaam — ek second mein shayad 1,000 combinations try kar le. toh **10 seconds mein hi tala khul jaayega.**

yahi brute force hai — **dimag nahi, speed kaam karti hai.**

---

### yeh attack kab aur kahan hota hai

brute force sirf password guess karna nahi hai — yeh kai jagah use hota hai:

| Target | Kya hota hai |
|---|---|
| **SSH login** | server ka username+password try karna |
| **FTP server** | file server pe ghusna |
| **Web login page** | website ka admin panel unlock karna |
| **ZIP/RAR file** | encrypted file ka password todna |
| **WiFi (WPA2)** | router ka password crack karna |
| **Email accounts** | ek ek password try karna |

---

### kitne types ke brute force hote hain

**1. Pure Brute Force**

aaaaa, aaaab, aaaac... aisa har ek combination khud try karta hai — koi list nahi, koi shortcut nahi. **slowest lekin guaranteed** — agar koi bhi combination wala password hai toh mil jaayega. bas bahut time lagta hai.

**2. Dictionary Attack** ← zyada famous aur practical

pehle se bani hui ek list (wordlist/dictionary) use karta hai — jisme duniya ke sabse zyada use hone wale passwords hote hain: `password`, `123456`, `admin`, `iloveyou`, `qwerty`, `letmein` wagera. **fast aur effective** — kyunki 80% log weak/common passwords rakhte hain.

**3. Hybrid Attack**

dictionary + variations — jaise `password1`, `Password!`, `p@ssword`, `P4ssw0rd`. kyunki log sochte hain number ya symbol daal diya toh safe ho gaya — hacker yahi exploit karta hai.

---

### ek zaroori cheez — wordlist

brute force ka engine hoti hai **wordlist** — ek simple text file jisme ek line pe ek password hota hai:

```
123456
password
admin
iloveyou
qwerty
letmein
123456789
password1
```

Kali Linux mein ek famous built-in wordlist aati hai — `/usr/share/wordlists/rockyou.txt` — isme **1.4 crore se zyada real passwords** hain jo ek purane hack mein leak hue the. yahi wordlist aaj bhi brute force attacks mein sabse zyada use hoti hai.

---

### tool — Hydra

brute force ke liye sabse famous aur widely used open-source tool hai — **Hydra**.

> Hydra ek aisa tool hai jo automatically ek ke baad ek password try karta rehta hai — tum bas batao kahan try karna hai (SSH, FTP, web login, etc.), kaunsa username hai, aur kaunsi wordlist use karni hai — baaki sab Hydra khud kar leta hai.

**Kali Linux mein:** Hydra **pehle se install** aata hai — koi install nahi karna.

```bash
hydra --version
```

agar nahi hai toh:

```bash
sudo apt install hydra
```

**Termux mein:**

```bash
pkg install hydra
```

dono jagah ek hi command chalti hai — syntax same hai.

---

### Hydra ki basic command — samjho kaise banta hai

```bash
hydra -l username -P wordlist.txt protocol://target
```

| Part | Matlab |
|---|---|
| `-l username` | jis username pe attack karna hai (lowercase L) |
| `-P wordlist.txt` | password list ki file |
| `protocol://target` | kahan attack karna hai — jaise `ssh://127.0.0.1` |

**example — SSH pe brute force:**

```bash
hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://192.168.1.1
```

iska matlab — `root` username pe, `rockyou.txt` ki list se ek ek password try karo, `192.168.1.1` ke SSH par.

jab password mil jaata hai toh Hydra yeh dikhata hai:

```
[22][ssh] host: 192.168.1.1   login: root   password: admin123
```

---

### yeh attack kyun kaam karta hai — aur kyun fail bhi hota hai

**kab kaam karta hai:**
- target ne weak/common password rakha ho
- account pe koi "login limit" na ho (baar baar try karne pe block na kare)
- target ka SSH ya FTP internet pe khula ho

**kab fail hota hai:**
- password strong aur unique ho (random characters, lamba)
- target pe **account lockout** ho — 5 galat tries ke baad account band
- **2FA (Two-Factor Authentication)** laga ho — password ke baad OTP bhi chahiye
- **rate limiting** ho — system deliberately slow down kare har try pe

> **yahi lesson hai asli hacking mein** — attack sirf tab kaam karta hai jab defense kamzor ho. strong password + 2FA + account lockout = Hydra bekar ho jaata hai.

---

### ek line mein

> **Brute Force ek speed-based attack hai jisme tool ek wordlist ki madad se ek ke baad ek password try karta rehta hai — dictionary attack mein common passwords ki list use hoti hai. Hydra is kaam ka sabse famous tool hai jo SSH, FTP, web aur doosre protocols pe kaam karta hai — strong password, account lockout aur 2FA isko rokne ke sabse effective tarike hain.**

---

## 🧠 MCQ Set — Topic 8.2

---

**Q1. Brute Force attack mein hacker kya karta hai?**

- A) System ki RAM overflow kar deta hai
- B) Virus inject karke password chura leta hai
- C) Ek trusted insaan ban ke victim ko call karta hai
- D) Ek ke baad ek passwords try karta rehta hai jab tak sahi na mile

**Sahi Jawab: D**
> Brute Force ka simple matlab hai — baar baar alag alag passwords try karna machine speed se, koi "trick" nahi.

---

**Q2. Dictionary Attack aur Pure Brute Force mein kya farq hai?**

- A) Dictionary Attack ek pre-made password list use karta hai, Pure Brute Force khud har combination try karta hai
- B) Dictionary Attack sirf numbers use karta hai
- C) Pure Brute Force zyada fast hota hai kyunki list nahi hoti
- D) Dono exactly same hain, sirf naam alag hai

**Sahi Jawab: A**
> Dictionary Attack common passwords ki ready-made list use karta hai — isiliye fast hota hai. Pure Brute Force khud sab combinations try karta hai — guaranteed lekin slow.

---

**Q3. Kali Linux mein famous built-in wordlist kahan hoti hai?**

- A) `/etc/passwords/rockyou.txt`
- B) `/home/kali/wordlists/rockyou.txt`
- C) `/usr/share/wordlists/rockyou.txt`
- D) `/var/hydra/rockyou.txt`

**Sahi Jawab: C**
> Kali Linux mein `rockyou.txt` — 1.4 crore se zyada leaked real passwords wali file — `/usr/share/wordlists/` mein milti hai.

---

**Q4. Hydra tool Termux mein install karne ka sahi command kya hai?**

- A) `sudo apt install hydra`
- B) `pip install hydra`
- C) `apt-get install hydra`
- D) `pkg install hydra`

**Sahi Jawab: D**
> Termux mein package manager `pkg` hota hai — `pkg install hydra` sahi command hai. `sudo apt` Debian/Kali ke liye hai.

---

**Q5. `hydra -l admin -P list.txt ssh://192.168.1.5` mein `-l admin` ka matlab kya hai?**

- A) Admin ko alert karo
- B) Log file ka naam `admin` rakho
- C) Admin wali language use karo
- D) Username `admin` use karke try karo

**Sahi Jawab: D**
> `-l` (lowercase L) matlab "login" — yani username. Is command mein `admin` username pe SSH brute force hoga.

---

**Q6. Brute Force attack rokne ka sabse effective tarika kya hai?**

- A) Strong unique password + 2FA + account lockout teeno saath
- B) Sirf username change karna kaafi hai
- C) Firewall install karna — yeh brute force rok deta hai akela
- D) Port number change karna — hacker ko pata nahi chalega

**Sahi Jawab: A**
> Akela ek step kaafi nahi — strong password + 2FA + account lockout teeno milke attack ko practically impossible bana dete hain.

---

**Q7. `rockyou.txt` wordlist kahan se aayi?**

- A) Kali Linux team ne khud banai
- B) MIT researchers ne AI se generate ki
- C) Ek purane real data breach mein leak hue actual passwords ka collection hai
- D) Yeh sirf fictional hai, koi real passwords nahi hain isme

**Sahi Jawab: C**
> RockYou ek company thi jiska 2009 mein breach hua — 1.4 crore users ke real passwords leak hue. Yahi passwords ab wordlist ban gaye hain.

---

**Q8. Account Lockout ka kya matlab hai?**

- A) Account ka password automatically change ho jaata hai
- B) System khud brute force karna shuru kar deta hai wapas
- C) Password hint email pe bhej deta hai
- D) Kuch galat tries ke baad account kuch time ke liye band ho jaata hai

**Sahi Jawab: D**
> Account lockout — jaise 5 galat tries ke baad 30 minute ke liye account block — brute force ko almost impossible bana deta hai.

---

**Q9. Hybrid Attack kya hota hai?**

- A) Dictionary words + variations try karna — jaise `password1`, `P@ssword`, `p4ssw0rd`
- B) Do alag hackers ek saath attack karte hain
- C) Pehle phishing karo, phir brute force karo
- D) Sirf uppercase passwords try karna

**Sahi Jawab: A**
> Hybrid Attack common words le ke unke variations try karta hai — kyunki log sochte hain number ya symbol daal diya toh password strong ho gaya.

---

**Q10. Hydra tool mainly kis cheez ke liye use hota hai?**

- A) Packet sniffing
- B) Malware banana
- C) Password brute forcing — SSH, FTP, web logins wagera pe
- D) IP spoofing

**Sahi Jawab: C**
> Hydra ek network login cracker hai — SSH, FTP, HTTP, Telnet aur 50+ protocols pe automated brute force karta hai.

---

**Q11. 2FA (Two-Factor Authentication) brute force se kaise bachata hai?**

- A) Password automatically reset ho jaata hai
- B) Sahi password mil bhi jaaye toh login ke liye ek aur step (OTP) chahiye — jo hacker ke paas nahi
- C) 2FA enable karne se password automatically strong ho jaata hai
- D) Hydra 2FA wale accounts skip kar deta hai

**Sahi Jawab: B**
> 2FA ka matlab — password ke baad bhi phone ya authenticator app se OTP chahiye. Hacker ke paas password aa bhi jaaye — login nahi kar sakta OTP ke bina.

---

**Q12. Pure Brute Force attack guaranteed kab hoga?**

- A) Jab target ka WiFi off ho
- B) Jab hacker ka internet fast ho
- C) Jab wordlist mein sahi password ho
- D) Technically hamesha — kyunki har combination eventually try hogi — lekin time bahut zyada lag sakta hai

**Sahi Jawab: D**
> Pure Brute Force mathematically guaranteed hai — har combination try hogi — lekin ek strong 12-character random password crack karne mein millions of years lag sakte hain.

---

**Q13. `hydra -l root -P wordlist.txt ssh://127.0.0.1` mein `127.0.0.1` kya hai?**

- A) Apna hi machine — localhost ka IP address
- B) Google ka server
- C) Hydra ka default target
- D) Wordlist ka location

**Sahi Jawab: A**
> `127.0.0.1` hamesha localhost hota hai — apna hi computer. Is command mein apne hi machine ke SSH pe brute force hoga — testing ke liye safe.

---

**Q14. Brute Force attack mein "Rate Limiting" kya karta hai?**

- A) Attack ki speed badhata hai
- B) Hacker ke IP ko permanently ban karta hai
- C) Password automatically change karta hai
- D) Har login attempt ke beech delay laata hai — tool slow ho jaata hai, attack practically ineffective

**Sahi Jawab: D**
> Rate limiting har try ke baad system ko deliberately slow karta hai — agar har attempt 2 second le toh 1 lakh passwords try karne mein 2 lakh second (55+ ghante) lagenge.

---

**Q15. Kali Linux mein Hydra already installed hai ya nahi — yeh confirm karne ka command kya hai?**

- A) `hydra install --check`
- B) `hydra --version`
- C) `sudo check hydra`
- D) `apt-cache show hydra`

**Sahi Jawab: B**
> `hydra --version` simply tool ka version print karta hai — agar Hydra installed hai toh version number dikhega, nahi hai toh "command not found" error aayega.

---

## 🛠️ Hands-On Task — Topic 8.2

**Goal:** Apne khud ke machine pe ek SSH server chalao, khud ek weak password set karo, aur phir Hydra se apna khud ka password "crack" karo — poora cycle khud dekho.

> ⚠️ **yeh task sirf apne khud ke machine pe hai — kisi aur ke server pe mat try karna. jo apna nahi hai usse attack karna illegal hai.**

---

**Step 1 — Hydra install karo (agar nahi hai)**

Kali Linux mein:
```bash
hydra --version
```
agar version dikhta hai — already hai, install ki zaroorat nahi.
nahi dikhta toh:
```bash
sudo apt install hydra
```

Termux mein:
```bash
pkg install hydra openssh
```

---

**Step 2 — Ek test user banao aur weak password set karo**

Kali Linux mein:
```bash
sudo adduser testuser
```
password poochenga — **`password123`** daalo (jaanboojhkar weak, taaki brute force demo kaam kare).

Termux mein (alag approach — Termux mein users nahi hote, isliye seedha SSH server chalate hain):
```bash
sshd
whoami
```
apna username note karo — wahi use hoga.

---

**Step 3 — SSH server chalu karo**

Kali Linux mein:
```bash
sudo systemctl start ssh
sudo systemctl status ssh
```
`Active: active (running)` dikhna chahiye.

Termux mein SSH server ek alag port pe chalta hai (default 8022):
```bash
sshd
```

---

**Step 4 — Ek mini wordlist banao jisme sahi password bhi ho**

```bash
nano mylist.txt
```

andar yeh likho:
```
admin
qwerty
123456
letmein
password123
iloveyou
abc123
hello
```

`password123` line mein hai — Hydra isko dhundh lega.

Save karo: `Ctrl+X` → `Y` → Enter.

---

**Step 5 — Hydra chalao**

Kali Linux mein:
```bash
hydra -l testuser -P mylist.txt ssh://127.0.0.1
```

Termux mein (port 8022):
```bash
hydra -l $(whoami) -P mylist.txt ssh://127.0.0.1 -s 8022
```

---

**Step 6 — Output dekho**

kuch aisa dikhega:

```
[DATA] attacking ssh://127.0.0.1:22/
[22][ssh] host: 127.0.0.1   login: testuser   password: password123
1 of 1 target successfully completed, 1 valid password found
```

> **yahi brute force hai.** tool ne ek ek password try kiya — 8 options mein se `password123` dhundh liya aur screen pe print kar diya. koi "hacking" nahi — sirf speed aur list ka kaam.

---

**Step 7 — Ab defender ban ke socho**

isi machine ke liye agar yeh 3 cheezein hoti — Hydra fail ho jaata:

1. **Strong password** — `xK9#mL2$pQr7` — koi wordlist mein nahi hoga
2. **Account lockout** — `sudo nano /etc/ssh/sshd_config` mein `MaxAuthTries 3` — 3 galat tries ke baad close
3. **2FA** — Google Authenticator ka OTP bhi maango SSH login pe

> **yahi asli ethical hacking ka lesson hai** — jab tum attack karna seekh lete ho, tab tumhe pata chalta hai defense kahan karna hai.

---

> 💡 **Tip:** `rockyou.txt` duniya ki sabse powerful wordlist hai — 1.4 crore real passwords. Agar tumhara password wahan hai toh koi bhi Hydra se crack kar sakta hai minutes mein. Check karo apna password — kya woh "common" lag raha hai? Agar haan — **abhi badlo.**

---

```
════════════════════════════════════════════════════════
   ✅  TOPIC 8.2 COMPLETE — BRUTE FORCE
   ⬇️  Neeche hai Topic 8.3
════════════════════════════════════════════════════════
```

---
