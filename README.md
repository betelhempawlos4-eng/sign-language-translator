# 🤟 Global Sign Language Translator

A real-time sign language translator that works directly in your browser using your webcam. No app install needed.

## ✅ Features

- 📷 **Live camera** — MediaPipe Hands detects 21 hand landmarks in real time
- 🧠 **3-layer detection engine:**
  - **Option A** — Rule-based ASL classifier (all 26 letters + common words, built-in)
  - **Option B** — Load your own Teachable Machine model via URL
  - **Option C** — Architecture guide for a full Python/Flask production backend
- 📊 **Live landmark inspector** — all 21 X/Y/Z coordinates updating every frame
- 📈 **Finger extension bars** — visualise how open/closed each finger is
- 🌍 **70+ sign languages** — select your country from the dropdown
- 🔊 **Text-to-speech** — hear the translation spoken aloud
- 📋 **Copy & history** — copy translated text, view detection log

## 🚀 Live Demo

> https://YOUR-APP-NAME.onrender.com

## 🛠 How to run locally

Just open `index.html` in your browser. For camera to work, use:

```bash
# Python 3
python -m http.server 8080
# Then open http://localhost:8080
```

Or use the VS Code Live Server extension.

## 📦 Deploy to Render (free)

1. Push this repo to GitHub
2. Go to render.com → New → Static Site
3. Connect your repo
4. Set Publish Directory to `.`
5. Click Create Static Site

Your site goes live at `https://your-app.onrender.com` ✅

## 📦 Deploy to GitHub Pages (free)

1. Push this repo to GitHub
2. Go to repo Settings → Pages
3. Source: Deploy from branch → main → / (root)
4. Save — live at `https://USERNAME.github.io/sign-language-translator`

## 🧠 Train your own model (Option A — Teachable Machine)

1. Go to [teachablemachine.withgoogle.com](https://teachablemachine.withgoogle.com)
2. New Project → Pose Project
3. Create a class per sign, record 30–50 samples each
4. Train → Export → TensorFlow.js → Upload (shareable link)
5. Paste the URL into the **Train** tab in the app

## 🏭 Production backend (Option C)

For full word-level recognition across languages:

```
Dataset:  WLASL (2,000 ASL words) — github.com/dxli94/WLASL
Extract:  MediaPipe landmarks per video frame
Train:    LSTM / Transformer on landmark sequences
Serve:    Flask API → /predict endpoint
Deploy:   Render Web Service
```

## 🔧 Tech stack

| Layer | Technology |
|---|---|
| Hand tracking | MediaPipe Hands (Google) |
| Gesture classification | Rule-based geometry + TF.js |
| Custom models | TensorFlow.js / Teachable Machine |
| Speech | Web Speech API |
| Hosting | Render / GitHub Pages |

## 📄 License

MIT — free to use, modify, and distribute.
