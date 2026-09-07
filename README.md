# E-Learning-wall
Phonics 
# 🔤 Interactive E-Learning Alphabet Wall

An interactive educational hardware installation designed for early childhood phonics learning. Built with an **Arduino Mega 2560**, a **3.5" TFT LCD Display**, **DFPlayer Mini MP3 module**, and a **PAM8406 Class-D stereo audio amplifier**, this board responds to 26 dedicated toggle switches topped with custom 3D-printed alphabet caps to display colorful typography and stream individual phonics songs.

---

## 🌟 Key Features

- **26 Physical Interactive Inputs:** Dedicated digital GPIO inputs mapped to A–Z toggle switches featuring 3D-printed letter caps.
- **State-Change / Edge-Trigger Logic:** Software debouncing and edge-detection architecture ensuring toggle switches trigger audio playback only on activation rather than looping indefinitely.
- **3.5" Color TFT Visuals:** High-contrast graphic rendering of uppercase and lowercase letters alongside phonics words using the `MCUFRIEND_kbv` and `Adafruit_GFX` graphics drivers.
- **Amplified Audio Playback:** Dual-channel amplified playback powered by a PAM8406 Class-D module driving external speakers via DFPlayer Mini.

---

## 🛠️ Hardware Stack & Pin Mapping

| Component | Interface / Pins | Arduino Mega Pinout |
| :--- | :--- | :--- |
| **3.5" TFT Shield** | 8-bit Parallel Bus | Directly mounted on Arduino Mega header shield |
| **DFPlayer Mini (RX)** | Serial1 TX | **Pin 18 (TX1)** (via 1kΩ resistor) |
| **DFPlayer Mini (TX)** | Serial1 RX | **Pin 19 (RX1)** |
| **PAM8406 Amplifier** | Audio In | Connected to DFPlayer Mini `DAC_R` / `DAC_L` / `GND` |
| **26 Toggle Switches** | Digital Inputs (Pull-up) | **Pins 22 to 47** $\rightarrow$ Common GND |

---

## 📂 SD Card Audio Organization

Format the micro-SD card to **FAT32** and organize the 26 song files inside an `mp3` directory with sequential 4-digit zero-padded filenames:

```text
SD_CARD/
└── mp3/
    ├── 0001.mp3   <-- (A Song)
    ├── 0002.mp3   <-- (B Song)
    ├── 0003.mp3   <-- (C Song)
    ...
    └── 0026.mp3   <-- (Z Song)
