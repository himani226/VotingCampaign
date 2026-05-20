# 🗳️ CEO Punjab – Voting Sweep AR Campaign

> A WebAR experience for the **Chief Electoral Officer, Punjab** — built to promote voter awareness through augmented reality. No app download needed. Works directly in the mobile browser.

---

## 📱 Live Demo

**Scan this QR or open the link on your phone:**
```
https://yourusername.github.io/your-repo-name/
```
> ⚠️ Replace with your actual GitHub Pages URL after deployment

---

## ✨ What It Does

When a voter points their phone camera at the **CEO Punjab logo** (on a poster, pamphlet, banner or screen):

- 🧍 A **3D character in traditional Punjabi dress** appears on the logo
- 🔊 She **speaks in Punjabi** automatically:
  > *"ਵੋਟ ਪਾਉਣਾ ਤੁਹਾਡਾ ਹੱਕ ਹੈ, ਇਸਨੂੰ ਇੰਝ ਨਾ ਗਵਾਓ। ਜੇ ਤੁਸੀਂ ਇਸ ਬਾਰੇ ਹੋਰ ਜਾਣਨਾ ਚਾਹੁੰਦੇ ਹੋ ਤਾਂ ਨੀਚੇ ਦਿੱਤੇ ਪੈਨਲਾਂ ਤੇ ਕਲਿੱਕ ਕਰੋ।"*
- 🌀 Tricolor confetti, orbiting info spheres and animations play
- 📋 Voter taps **info panels** to learn about:
  - ⚖️ Constitutional right to vote (Article 326)
  - 🗳️ Step-by-step voting guide
  - 🪪 Voter ID & accepted alternatives
  - ❌ Common myths — busted in Punjabi
  - 🙏 Voter's pledge with share button

---

## 🗂️ File Structure

```
ceo-punjab-ar/
├── index.html                           # Main app — lightweight ~28KB
├── target.mind                          # Compiled MindAR image target (CEO Punjab logo)
├── images.png                           # CEO Punjab logo image
├── traditional_dress_girl_3d_model.glb  # 3D character model
└── README.md                            # This file
```

---

## 🛠️ Tech Stack

| Tool | Purpose | Cost |
|------|----------|------|
| [MindAR.js](https://hiukim.github.io/mind-ar-js-doc/) | Image target tracking | Free & Open Source |
| [A-Frame 1.5](https://aframe.io) | 3D / WebXR scene | Free & Open Source |
| Web Speech API | Punjabi text-to-speech | Built into browser |
| GitHub Pages | Hosting & delivery | Free |

**No paid SDK. No backend. No app store. 100% open source.**

---

## 🚀 How to Deploy

### Step 1 — Generate `target.mind`

Go to the free MindAR compiler (no account needed):
👉 https://hiukim.github.io/mind-ar-js-doc/tools/compile

1. Upload `images.png` (CEO Punjab logo)
2. Click **Start** — compiles in browser, takes ~30 seconds
3. Download the file → rename to `target.mind`
4. Place it in the repo root

### Step 2 — Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit – CEO Punjab Voting AR"
git branch -M main
git remote add origin https://github.com/yourusername/your-repo-name.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. Go to your repo → **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** → Folder: **/ (root)**
4. Click **Save**
5. Your URL will be live in ~60 seconds:
   `https://yourusername.github.io/your-repo-name/`

### Step 4 — Share via QR Code

Generate a QR code from your GitHub Pages URL at:
👉 https://www.qr-code-generator.com

Print on posters, pamphlets, banners, voter slips — anywhere the CEO Punjab logo appears.

---

## 📲 How Voters Use It

```
1. Voter scans QR code on poster/pamphlet
       ↓
2. Link opens in Chrome (Android) or Safari (iOS)
       ↓
3. Tap "AR ਸ਼ੁਰੂ ਕਰੋ · Start AR"
       ↓
4. Allow camera access
       ↓
5. Point camera at CEO Punjab logo
       ↓
6. 3D character appears + speaks in Punjabi 🎤
       ↓
7. Tap info cards to explore voting rights
```

---

## 📱 Device Compatibility

| Device | Browser | Status |
|--------|---------|--------|
| Android (mid-range+) | Chrome | ✅ Full support |
| iPhone (iOS 15+) | Safari | ✅ Full support |
| Desktop | Chrome / Edge | ✅ Works (webcam required) |
| Android | Firefox | ⚠️ Partial |

> **Punjabi voice quality** depends on the device. Android phones with Google TTS give the best `pa-IN` voice. If Punjabi voice is unavailable, app automatically falls back to Hindi voice with romanised Punjabi text.

---

## 🔧 Customisation Guide

### Change the 3D model
Replace `traditional_dress_girl_3d_model.glb` with any `.glb` file and update the filename in `index.html`:
```html
<a-asset-item id="girl-model" src="your-new-model.glb"></a-asset-item>
```

### Change the image target
1. Replace `images.png` with your new target image
2. Recompile `target.mind` at https://hiukim.github.io/mind-ar-js-doc/tools/compile
3. Replace the old `target.mind` in the repo

### Change the Punjabi speech text
In `index.html`, find the `speakPunjabi()` function and edit `msg.text`:
```javascript
msg.text = 'ਆਪਣਾ ਨਵਾਂ ਸੁਨੇਹਾ ਇੱਥੇ ਲਿਖੋ';
```

### Change the model scale / position
Find `<a-entity id="girl-entity">` in `index.html` and adjust:
```html
scale="0.4 0.4 0.4"   <!-- increase for bigger model -->
position="0 0 0"       <!-- x y z offset from marker center -->
```

### Add more languages
Duplicate the `speakPunjabi()` function and change `msg.lang`:
```javascript
msg.lang = 'hi-IN';  // Hindi
msg.lang = 'en-IN';  // English (Indian)
msg.lang = 'pa-IN';  // Punjabi (default)
```

---

## 📋 Info Panels Content

All 5 info panels are in **Punjabi + English** and cover:

| Panel | Content |
|-------|---------|
| ⚖️ ਵੋਟ ਦਾ ਅਧਿਕਾਰ | Article 326, universal suffrage, secret ballot |
| 🗳️ ਵੋਟ ਕਿਵੇਂ ਪਾਈਏ | 6-step voting guide from registration to VVPAT |
| 🪪 ਵੋਟਰ ID | EPIC card + 6 accepted photo ID alternatives |
| ❌ ਭਰਮ-ਭੁਲੇਖੇ | 4 common myths debunked in Punjabi |
| 🙏 ਮਤਦਾਤਾ ਸਹੁੰ | ECI voter's pledge with native share button |

---

## 🏛️ About

Built for the **Chief Electoral Officer, Punjab** as part of the **Systematic Voters' Education and Electoral Participation (SVEEP)** campaign.

- **Purpose:** Increase voter turnout through immersive AR awareness
- **Target audience:** First-time voters, rural voters, youth
- **Language:** Punjabi (ਪੰਜਾਬੀ) with English support
- **Delivery:** QR code on existing election materials — zero extra cost

---

## 📞 Voter Helpline

**1950** — National Voter Helpline (free, available in Punjabi)

🌐 **voters.eci.gov.in** — Register / check your name on electoral roll

---

## 📄 License

This project is open source and free to use for government electoral awareness campaigns.

---

*ਵੋਟ ਪਾਓ। ਆਪਣਾ ਹੱਕ ਵਰਤੋ। 🗳️*
*Vote. Exercise your right.*
