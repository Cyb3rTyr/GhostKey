# 👻 Ghostkey

**Ghostkey** is a compact, open-source plug-and-play USB device inspired by Rubber Ducky and Flipper Zero.  
It delivers preconfigured or custom keyboard injection payloads to Windows, macOS, and Linux — powered by a pixel-art mascot and a stealthy UI.

---

## 📦 Features

- 🧠 Smart HID injection with OS detection
- 🎭 Pixel-art mascot with multiple expression states (idle, executing, success, error, etc.)
- 📂 Custom script support via microSD card
- 🚫 No internal script storage — runs and clears after execution
- ⚡ Auto-execute when plugged in, no menus needed unless SD is used
- ✅ All payloads editable externally
- 🎨 Clean, themed UI with mascot integration

---

## 🛠️ Tech Stack

- **Device:** M5Stack Cardputer (ESP32-S3)
- **Firmware:** Arduino / C++
- **Display:** 135x240px TFT (16-bit color)
- **Script Storage:** 
  - `SPIFFS` for UI assets (PNG)
  - `microSD` for user payloads
- **Libraries:** 
  - M5Unified  
  - PNGDecoder  
  - SD  
  - HID-Project

---

## 📁 Folder Structure

```plaintext
Ghostkey/
│
├── data/                      # SPIFFS files (PNGs)
│   ├── ghostkey_idle.png
│   ├── ghostkey_executing.png
│   ├── ghostkey_success.png
│   ├── ghostkey_error.png
│   ├── ghostkey_loading.png
│   └── ghostkey_low_battery.png
│
├── scripts/                   # SD Card payloads
│   ├── Windows/
│   ├── Linux/
│   ├── macOS/
│   └── Custom/
│
├── src/
│   ├── ghostkey.ino
│   └── payload_parser.cpp
│
└── README.md


---

## ⚙️ Getting Started

### Prerequisites

- Arduino IDE
- ESP32 board manager URL:  
  `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json`
- Install libraries: `M5Unified`, `HID-Project`, `PNGDecoder`, `SD`

### Flashing Instructions

1. Place your PNG mascot images in `/data/`
2. Upload them to SPIFFS with `Tools > ESP32 Sketch Data Upload`
3. Load and flash `ghostkey.ino` to your M5Stack Cardputer
4. Insert a microSD with your scripts organized in folders
5. Plug Ghostkey into a PC — and let the mischief begin 👻

---

## 💡 Usage Flow

- When plugged into a system:
  - If no SD card is inserted: show mascot animation and wait
  - If SD present: allow user to scroll scripts and select by OS
  - Selected script runs instantly
  - Mascot shows success or error face afterward

---

## 📜 Legal Disclaimer

This tool is intended **strictly for educational and authorized auditing purposes**.  
You are responsible for using this tool in accordance with all applicable laws.  
The author disclaims all liability for misuse or damage caused by this project.

Payloads referencing [Hak5](https://hak5.org) repositories are not bundled directly and follow their license requirements.

---

## 📸 UI Example

*(Replace with real screenshots later)*  
![Mascot](docs/images/ghostkey_idle.png)  
*Idle Ghostkey ready to hack.*

---

## 📫 Contact

Feel free to submit issues, feature ideas, or mascot improvements!

> Inspired by Flipper Zero, Rubber Ducky, and Pwnagotchi.  
> Ghostkey is open-source and not for sale — only shared for education and fun.
