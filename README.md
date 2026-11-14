# LiveCam — web app (camera + mike, do phone connect)

Ek phone **Camera** banta hai, doosra **Viewer**. Viewer me ek chhota code daalo, live video+awaaz aa jati hai.
WebRTC (WhatsApp call wali tech) use hoti hai, PeerJS signaling ke saath.

## Files
| file | kaam |
|---|---|
| `index.html` | poori app (camera + viewer + saari logic) |
| `manifest.json` + `icon.svg` | "Add to Home Screen" (app jaisa install) |
| `sw.js` | service worker — PWA install ke liye |

---

## Host kaise karein — 2 aasan tareeqe

### Tareeqa A — Netlify Drop (sabse fast, 1 minute)
1. PC browser me kholo: **https://app.netlify.com/drop**
2. Is `webcam-app` folder ko (pura folder) page par **drag & drop** kar do.
3. Thodi der me ek live URL milega, jaise `https://random-name-123.netlify.app`
4. Bas! Wahi URL dono phone me kholo.
   - (Login kiye bina URL kuch ghante rehta hai. Permanent chahiye to free account bana lo.)

### Tareeqa B — GitHub Pages (permanent, free)
1. GitHub par account banao, ek naya **public repository** banao (jaise `livecam`).
2. Is folder ki saari files us repo me upload karo (web se "Add file → Upload files").
3. Repo → **Settings → Pages** → Source: `main` branch, `/root` → Save.
4. 1-2 min me URL milega: `https://<tumhara-username>.github.io/livecam/`

> **Zaroori:** URL `https://` hona chahiye (dono tareeqe HTTPS dete hain). `http://` ya file se kholne par camera **nahi** chalega — ye browser ka rule hai.

---

## Chalana (dono phone)
1. **Phone 1 (camera):** URL kholo → **📷 Camera banao** → camera+mic ki permission **Allow**.
   Screen par ek **code** aayega (jaise `K7P2Q9`).
2. **Phone 2 (viewer):** wahi URL kholo → **👁️ Dekho** → wo code daalo → **Connect**.
   Live video+awaaz aa jayegi.
3. **App jaisa install:** Chrome menu (⋮) → **"Add to Home screen"** → icon ban jayega.

## Tips
- Dono phone internet par hone chahiye (PeerJS ka signaling online hai). Zyada data nahi lagta.
- Awaaz na aaye to viewer me video par **ek baar tap** karo (browser autoplay rokta hai).
- Camera phone ki screen on rehni chahiye (app usse awake rakhti hai).

## Sirf apne liye
Apne hi devices aur apni jagah par use karo. Kisi ko bina ijaazat record/nigrani karna galat aur gair-qanooni hai.

## Aage (phase 2)
- Password/PIN taaki koi aur code guess karke na judey.
- Recording (MediaRecorder se video save).
- Ek camera, kai viewers.
- Apna signaling server (PeerJS khud host karke, public cloud ki jagah).
