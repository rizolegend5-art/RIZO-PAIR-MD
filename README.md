# RIZO-MD Pair Site — Vercel Deploy Package

Yeh ek **standalone** pairing website hai (sirf frontend). Yeh khud WhatsApp se connect nahi hoti — asal
bot (session banana, QR/code dena) Railway par chal raha aap ka `RIZO-MD` server hi karta hai:

```
https://rizo-mini-bot-production-21495631.up.railway.app
```

Yeh Vercel page sirf us Railway server se baat karta hai (`/api/servers`, `/code`, `/status` wagera), taake
aap ka pairing page kisi bhi naam/domain se Google par aa sake, Railway ke `.up.railway.app` link se alag.

## Deploy (2 minute)
1. Is folder ko GitHub repo bana kar push karein, ya seedha [vercel.com/new](https://vercel.com/new) par
   is folder ko drag-drop/upload karein (Framework: "Other", koi build command nahi chahiye).
2. Deploy hone ke baad Vercel apna link dega, misal `rizo-pair.vercel.app` — ya Project Settings > Domains
   se apna custom domain (jaise `rizomd.com`) laga sakte hain.
3. In teen files mein `YOUR-VERCEL-DOMAIN.vercel.app` ko apne asal domain se badal dein (find & replace):
   - `index.html` (4 jagah — canonical link, og:url, aur 2 JSON-LD `url` fields)
   - `robots.txt`
   - `sitemap.xml`
4. Dobara deploy (push) karein.

## Zaroori: Railway ka naya link badal jaye to
Agar aap Railway par naya deploy karte hain aur link badal jaye, to `index.html` mein yeh 2 jagah dhoondh
kar naya link likhein:
```
https://rizo-mini-bot-production-21495631.up.railway.app
```

## Google par aane ke liye
1. [Google Search Console](https://search.google.com/search-console) par apna Vercel domain add karein.
2. Verification tag `index.html` ke `<head>` mein jahan likha hai
   `<!-- Google Search Console verification tag: paste it here -->`, wahan apni meta tag paste karein.
3. Sitemap (`sitemap.xml`) submit karein, aur home page par "Request Indexing" dabayein.
4. Google ko dikhne mein (khaaskar naye domain ke liye) din se hafte lag sakte hain — yeh Google decide
   karta hai, koi bhi website isay guarantee nahi kar sakti.

## Yeh kis cheez ke liye NAHI hai
- Yahan pair.html ka woh hissa jo sirf bot ke apne server par chalta hai (jaise `.code` AI command ka
  preview, ya WhatsApp se seedha connect hona) is static page mein nahi hai — wo sab Railway ke bot process
  mein hi rehta hai. Yeh sirf uska **pairing page ka frontend mirror** hai.
