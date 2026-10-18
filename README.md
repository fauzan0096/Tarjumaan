# Hum Tum 💞 — long-distance couple app

Ek hi `index.html` app: encrypted journal + live chat + games + Saudi/India clocks.

## GitHub Pages par chalana
1. Naya repo banao, in 5 files upload karo: `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`.
2. Settings → Pages → branch `main`, folder `/ (root)`.
3. HTTPS link dono phones par Chrome/Safari mein kholo → "Add to Home screen".
4. Dono apna alag passphrase banao. Phir **Together** tab: ek banda "New code" banaye, WhatsApp par bheje, dusra wahi code/link use kare.

## Kya kaise kaam karta hai
- Journal/notes/chat history sirf aapke phone mein, AES-GCM + PBKDF2 (600k) se encrypted.
- Live chat/games public MQTT servers se guzarte hain, par poora content room code se bani key se encrypted hota hai.
- **Offline messages:** aap ke last 30 messages encrypted form mein broker par retained rehte hain. Partner baad mein app khole to mil jaate hain. Ye best-effort hai, guarantee nahi.
- Aaj ka sawal/challenge dono ko same dikhta hai (Riyadh date se).

## Sach (limits)
- Server par content encrypted hai, lekin **metadata** (IP, timing, room topic) public servers dekh sakte hain.
- Free public servers kabhi slow/down/block ho sakte hain. Isliye 5 servers ek saath use hote hain.
- Push notification nahi hai: app band ho to alert nahi milega.
- Room code kamzor mat rakho (e.g. "iloveyou"); "New code" wala use karo.
- Chat clear karne ke baad broker se purane messages wapas aa sakte hain.
- Passphrase bhoolne par data recover nahi hota. Vault tab se encrypted backup lete raho.
- Ye audited security product nahi hai. Repo mein koi personal data/backup commit mat karo.
