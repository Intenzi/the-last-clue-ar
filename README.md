# The Last Clue — AR Detective Scavenger Hunt

A 3–5 minute WebAR crime investigation experience designed for mobile and web browsers.

## 📁 Project Structure
```
the-last-clue-ar/
├── index.html                   # Complete WebAR Game Engine (MindAR + Three.js)
├── README.md                    # Setup & GitHub Pages Deployment Guide
└── assets/
    ├── audio/                   # 16-bit 44.1kHz Synthesized Audio Stingers
    │   ├── case_solved.wav
    │   ├── clue_found.wav
    │   ├── tick.wav
    │   └── try_again.wav
    ├── models/                  # Ultra-lightweight glTF 2.0 Binary Props (<15 KB each)
    │   ├── brass_paperweight.glb
    │   ├── broken_glass.glb
    │   └── broken_watch.glb
    ├── targets/                 # Pre-compiled MindAR Image Tracking Targets
    │   ├── card.mind
    │   └── card.png
    └── textures/                # 2D Transparent Decals & Dossier Marker
        ├── footprint.png
        ├── target_marker.png
        └── threatening_letter.png
```

---

## 🚀 How to Host on GitHub Pages (Free, 2 Minutes)

GitHub Pages gives you free **HTTPS** hosting (which is strictly required by iOS Safari and Android Chrome to grant camera access).

1. In your terminal, initialize and push the repository:
   ```bash
   cd "/Users/tenzi/Documents/My Projects/the-last-clue-ar"
   git init
   git add .
   git commit -m "Initial commit: The Last Clue WebAR"
   gh repo create the-last-clue-ar --public --source=. --push
   ```
2. Enable GitHub Pages:
   * Go to **GitHub Repo → Settings → Pages**.
   * Under **Branch**, select `main` and `/ (root)`.
   * Click **Save**.
3. Your game is live immediately at:
   `https://<your-username>.github.io/the-last-clue-ar/`
4. Generate a QR code for that URL. Anyone at the college exhibition can scan the QR code with their phone camera to play immediately.

---

## 💻 Local Testing (Without Deploying)

Because browsers block camera access on raw `file://` URLs, run a fast local server:
```bash
cd "/Users/tenzi/Documents/My Projects/the-last-clue-ar"
python3 -m http.server 8080
```
Open `http://localhost:8080` in your browser.

---

## 🎮 How to Play

1. **Dual Investigation Modes:**
   * **📷 Start WebAR (Camera Mode):** Point your phone camera at `assets/targets/card.png` (either printed on paper or displayed on another phone/laptop screen). The crime scene anchors to the surface.
   * **🖥️ Virtual 3D Investigation:** Orbit, zoom, and click the clues in a 3D virtual study room directly on any desktop or phone without needing camera permissions or paper prints.
2. **Investigation Loop:**
   * Tap on each of the 5 clues (Broken Watch, Broken Glass, Threatening Letter, Muddy Footprint, Brass Paperweight) to inspect forensic notes.
   * Collected clues light up in your HUD inventory bar.
3. **The Deduction:**
   * Once all 5 clues are found, click **Identify Murder Weapon**.
   * Pick between *Broken Glass*, *Brass Paperweight*, and *Broken Watch*.
   * Correct deduction reveals the **CASE SOLVED** verdict.
