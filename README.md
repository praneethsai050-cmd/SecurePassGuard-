<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,18,24,28&height=220&section=header&text=SecurePassGuard&fontSize=48&fontAlignY=35&animation=twinkling&fontColor=ffffff" />
</p>

<p align="center">
  <b>Client-Side Password Entropy Analyzer & Cryptographic Generator</b><br>
  <i>Real-time password vulnerability detection, heuristic scoring, and zero-knowledge security analysis.</i>
</p>

<p align="center">
  <a href="https://github.com/praneethsai050-cmd/SecurePassGuard-">
    <img src="https://img.shields.io/badge/Security-Zero--Knowledge_Client--Side-10B981?style=for-the-badge&logo=shield&logoColor=white" />
  </a>
  <a href="https://praneethsai050-cmd.github.io">
    <img src="https://img.shields.io/badge/Author-A._Praneeth_Sai-8B5CF6?style=for-the-badge&logo=googlechrome&logoColor=white" />
  </a>
  <a href="https://wa.me/918777679256?text=Hi%20Praneeth%2C%20saw%20SecurePassGuard%20and%20wanted%20to%20connect!">
    <img src="https://img.shields.io/badge/WhatsApp-+91_87776_79256-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" />
  </a>
  <a href="https://youtube.com/@flixyte">
    <img src="https://img.shields.io/badge/YouTube-@flixyte-FF0000?style=for-the-badge&logo=youtube&logoColor=white" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/Storage-LocalStorage_API-007ACC?style=flat-square" />
  <img src="https://img.shields.io/badge/Architecture-100%25_In--Memory-10B981?style=flat-square" />
  <img src="https://img.shields.io/badge/License-MIT-purple?style=flat-square" />
</p>

---

## 📑 Table of Contents
- [Executive Overview](#-executive-overview)
- [The Threat Vector: Why Entropy Matters](#-the-threat-vector-why-entropy-matters)
- [Key Features & Capabilities](#-key-features--capabilities)
- [Mathematical Entropy & Heuristic Engine](#-mathematical-entropy--heuristic-engine)
- [Brute-Force & Crack-Time Comparison](#-brute-force--crack-time-comparison)
- [Zero-Knowledge Architecture Guarantee](#-zero-knowledge-architecture-guarantee)
- [Quickstart & Local Installation](#-quickstart--local-installation)
- [Code Architecture](#-code-architecture)
- [About the Author](#-about-the-author)
- [Direct Transmission Hub](#-direct-transmission-hub)

---

## ⚡ Executive Overview

**SecurePassGuard** is an interactive, browser-based cybersecurity tool engineered to calculate password entropy, detect structural cryptographic vulnerabilities, and generate high-entropy passwords. 

Unlike conventional online password checkers that upload keystrokes to third-party endpoints or cloud APIs, **SecurePassGuard operates with an absolute zero-knowledge guarantee**: 100% of regex parsing, character space calculations, and generation routines occur purely in client-side volatile memory.

---

## 🎯 The Threat Vector: Why Entropy Matters

With modern GPU rigs (e.g., 8× RTX 4090 clusters) capable of calculating over **100+ billion NTLM / MD5 hashes per second**, traditional 8-character passwords composed of predictable strings (`Password123!`) succumb to dictionary and hybrid mask attacks within seconds.

Common vulnerabilities detected by SecurePassGuard:
1. **Low Pool Cardinality:** Passwords restricted to lowercase alphabets ($R = 26$) collapse under simple exhaustive search.
2. **Consecutive Repetition Vulnerabilities:** Repetitions like `aaaa` or `1111` drastically degrade true information entropy.
3. **Predictable Substring Patterns:** Human habit substitutions (`@` for `a`, `0` for `o`) easily cracked via Hashcat rule-tables.

---

## 🚀 Key Features & Capabilities

```
┌────────────────────────────────────────────────────────────────────────┐
│                        SECUREPASSGUARD WORKFLOW                        │
└────────────────────────────────────────────────────────────────────────┘
          │
          ├──► [ Keystroke Stream Input ] (Conceal / Reveal Toggle)
          │
          ├──► [ Real-Time Heuristic Scanner ]
          │      • Length Verification (8+, 12+, 16+ bonus)
          │      • Character Cardinality Check ([A-Z], [a-z], [0-9], symbols)
          │      • Pattern / Anomaly Detection (consecutive char repetitions)
          │
          ├──► [ Multi-Tier Visual Entropy Meter ]
          │      • Weak (20% - 40%) ➔ Moderate (60%) ➔ Strong (80%) ➔ Very Strong (100%)
          │      • Real-time contextual remediation suggestions
          │
          └──► [ Cryptographic Password Generator ]
                 • Granular charset toggles (Uppercase, Lowercase, Digits, Symbols)
                 • 8 to 32 character slider
                 • Browser LocalStorage persistence for user preferences
```

### 1. 🔍 Real-Time Heuristic Scoring
- Evaluates 5 core cryptographic criteria simultaneously with instant visual feedback badges (`✅` / `❌`).
- Dynamic bonus weighting rewards passwords exceeding 12 and 16 characters.

### 2. 💡 Contextual Remediation Engine
- Generates proactive, actionable suggestions:
  - *"Consider using 12+ characters for better security"*
  - *"Avoid repeating characters"*
  - *"Add special characters (!@#$%^&*)"*

### 3. 🎲 Granular Cryptographic Generator
- Generates unguessable passwords between **8 and 32 characters**.
- Configurable switches for uppercase, lowercase, numbers, and special characters.
- One-click clipboard copy utility with animated toast alerts.

### 4. 💾 Client-Side Preference Persistence
- Saves preferred generator parameters into the browser's `localStorage` (`securePassGuardPrefs`), eliminating repetitive reconfiguration across sessions.

---

## 📐 Mathematical Entropy & Heuristic Engine

Information entropy $E$ (measured in bits) defines the resistance of a password against brute-force attacks:

$$E = L \times \log_2(R)$$

Where:
- $L$ = Length of the password (number of characters)
- $R$ = Cardinality of the character pool:
  - Lowercase only (`a-z`): $R = 26$
  - Mixed case (`a-z, A-Z`): $R = 52$
  - Alphanumeric (`a-z, A-Z, 0-9`): $R = 62$
  - Full ASCII printable charset: $R = 94$

### Scoring & Entropy Classification

| Score Threshold | Categorization | Visual Color | Typical Entropy Range | Brute-Force Complexity ($2^E$) |
| :---: | :---: | :---: | :---: | :---: |
| **0 – 2** | `Weak` | 🔴 `#ff4444` / `#ff8800` | $< 35$ bits | Trivial ($\le$ seconds) |
| **3** | `Moderate` | 🟡 `#ffbb33` | $35 – 55$ bits | Vulnerable ($\le$ hours / days) |
| **4** | `Strong` | 🟢 `#00C851` | $56 – 75$ bits | Resilient ($\le$ decades) |
| **5 – 7** | `Very Strong` | 🟢 `#007E33` | $> 75$ bits | Cryptographically Secure (Millennia+) |

---

## ⏱️ Brute-Force & Crack-Time Comparison

*Assumes a high-end enterprise attack cluster testing at $10^{11}$ hashes/sec:*

| Password Example | Length | Character Pool | Est. Entropy | Typical Crack Time |
| :--- | :---: | :--- | :---: | :--- |
| `password` | 8 | Lowercase only ($R=26$) | ~37.6 bits | **< 0.002 Seconds** |
| `P@ssw0rd` | 8 | Mixed + Digits + Symbol ($R=94$) | ~52.4 bits | **< 48 Seconds** |
| `SecurePass2026` | 14 | Alphanumeric ($R=62$) | ~83.3 bits | **~3,000+ Years** |
| `K9#mQ!8$zL2@vP4&` | 16 | Full ASCII ($R=94$) | ~104.8 bits | **Centuries (Unhackable)** |

---

## 🛡️ Zero-Knowledge Architecture Guarantee

Security and privacy are foundational to this tool:
- 🚫 **No Analytics or Telemetry:** No tracking scripts, Google Analytics, or external beacons.
- 🚫 **No Network Transmissions:** Zero `fetch()`, `XMLHttpRequest`, or `WebSocket` calls.
- 🔒 **Volatile Memory Execution:** Keystrokes are evaluated solely within DOM memory and discarded upon page refresh.
- 🌐 **Offline First:** Fully functional without an active internet connection (works directly via `file://`).

---

## 🛠️ Quickstart & Local Installation

### Method 1: Direct File Launch (Zero Dependencies)
```bash
# Clone the repository
git clone https://github.com/praneethsai050-cmd/SecurePassGuard-.git
cd SecurePassGuard-

# Open directly in default web browser
# Windows:
start index.html
# macOS:
open index.html
# Linux:
xdg-open index.html
```

### Method 2: Local HTTP Server (Python)
```bash
python -m http.server 8080
```
Open **`http://localhost:8080`** in your browser.

---

## 📂 Code Architecture

```
SecurePassGuard-/
├── index.html                   # Root entry point (Self-contained app)
├── SecurePassGuard/
│   └── index.html               # Module view
├── LICENSE                      # MIT Open Source License
└── README.md                    # Comprehensive technical documentation
```

### Key Logic Implementations
- `analyzePassword(password)`: Executes regex audits (`/[A-Z]/`, `/[a-z]/`, `/[0-9]/`, `/[!@#$%^&*...]/`), computes aggregate scores, and sets UI color states.
- `generatePassword()`: Pulls active character sets based on user toggles, uses browser pseudo-random selection, and updates the input field.
- `savePreferences()` / `loadPreferences()`: Manages `localStorage` key `securePassGuardPrefs`.

---

## 👨‍💻 About the Author

**A. Praneeth Sai**  
*1st-Year B.Tech CSE (Cyber Security) @ Jaypee University of Information Technology (JUIT), Waknaghat, Solan*

- 🛡️ **Flagship Venture:** Founder & Lead Backend Architect of **[Satyameva Aegis](https://github.com/praneethsai050-cmd/satyameva)** (Custom PoW Blockchain & Biometric Credentialing).
- 🏆 **Hackathons:** Selected for **RIDEHACK'26 Grand Finals** (1st Nov 2026 @ JIIT Noida • Team ID: 10) & Team Leader for **Smart India Hackathon 2026** (`PS: SIH26125`).
- 🎬 **Content Creator:** Documenting college engineering hustle, Linux internals, and hackathons on YouTube **[@flixyte](https://youtube.com/@flixyte)**.
- 🌐 **Interactive Portfolio:** **[praneethsai050-cmd.github.io](https://praneethsai050-cmd.github.io)**

---

## 📬 Direct Transmission Hub

<p align="center">
  <a href="https://wa.me/918777679256?text=Hi%20Praneeth%2C%20saw%20SecurePassGuard%20and%20wanted%20to%20connect!">
    <img src="https://img.shields.io/badge/WhatsApp-+91_87776_79256-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/a-praneeth-sai-089023289/">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://youtube.com/@flixyte">
    <img src="https://img.shields.io/badge/YouTube-@flixyte-FF0000?style=for-the-badge&logo=youtube&logoColor=white" />
  </a>
  <a href="mailto:261034004@juitsolan.in">
    <img src="https://img.shields.io/badge/Academic_Email-261034004@juitsolan.in-8B5CF6?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="mailto:praneethsai050@gmail.com">
    <img src="https://img.shields.io/badge/Personal_Email-praneethsai050@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>

<p align="center">
  <a href="https://praneethsai050-cmd.github.io">
    <img src="https://img.shields.io/badge/🌐_Visit_My_Interactive_Web_Portfolio-10B981?style=for-the-badge&logoColor=white" />
  </a>
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,18,24,28&height=100&section=footer" />
</p>

<p align="center">
  <b>SecurePassGuard</b> • <i>"Advancing user security through cryptographic transparency."</i>
</p>
