<div align="center">

# 🎯 ValoAim V1.5

[![License](https://img.shields.io/badge/License-Licensed-blue.svg)](https://github.com/yourusername/valoaim)
[![Version](https://img.shields.io/badge/Version-1.5-green.svg)](https://github.com/yourusername/valoaim/releases)
[![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)](https://www.microsoft.com/windows)
[![Python](https://img.shields.io/badge/Python-3.8+-yellow.svg)](https://python.org)

*A sophisticated computer vision-based aim assistance tool with customizable settings and hardware integration support.*

</div>

---

## 📋 Table of Contents
- [✨ Features](#-features)
- [🔧 Installation](#-installation)
- [⚙️ Setup](#️-setup)
- [📝 Configuration](#-configuration)
- [🚀 Usage](#-usage)
- [⌨️ Key Bindings](#️-key-bindings)
- [🔍 Troubleshooting](#-troubleshooting)

---

## ✨ Features

- 🎯 **Aim Assistance**: Customizable aim smoothing and speed
- 🔄 **Recoil Compensation**: Automatic recoil control with adjustable patterns
- ⚡ **Trigger Bot**: Automated shooting with configurable delays
- 🔥 **Rapid Fire**: Customizable click rate automation
- 🔌 **Hardware Integration**: Serial communication and driver support
- 📊 **Real-time UI**: Console-based interface with live status updates
- 🔐 **License Management**: Secure key-based authentication

## 🔧 Installation

### 📋 Prerequisites
- 🪟 Windows 10/11
- 🐍 Python 3.8+ (if running from source)
- 📦 Required Python packages (see requirements below)

### 📦 Required Python Packages
```bash
pip install numpy opencv-python bettercam pyautogui pyserial colorama win32api configparser requests
```

### 🖥️ Hardware Requirements
- 🔌 Compatible serial device (if using serial communication)
- 📺 Screen resolution: 1920x1080 recommended

---

## ⚙️ Setup

1. 📁 **Download/Clone** the project files
2. 📄 **Place config.ini** in the same directory as the executable/script
3. 🔑 **Configure your license key** in config.ini
4. ⚙️ **Adjust settings** according to your preferences
5. ▶️ **Run the application**

## 📝 Configuration

The `config.ini` file contains all customizable settings organized in sections:

### 🔐 [license]
```ini
key = YOUR-LICENSE-KEY-HERE
```
- **key**: Your valid license key for authentication

### 📡 [communication]
```ini
com_port = COM3
```
- **com_port**: Serial communication port (e.g., COM3, COM4)
- **type**: Communication type (none, driver, serial, socket) - defaults to serial

### 🖥️ [screen]
```ini
detection_threshold = 3, 3
upper_color = 10, 255, 255
lower_color = 0, 165, 150
fov_x = 100
fov_y = 100
aim_fov_x = 80
aim_fov_y = 70
fps = 165
auto_detect_resolution = false
resolution_x = 1920
resolution_y = 1080
min_target_area = 25
```

- **detection_threshold**: Detection sensitivity (x, y)
- **upper_color**: Upper HSV color range for detection (H, S, V)
- **lower_color**: Lower HSV color range for detection (H, S, V)
- **fov_x/fov_y**: Field of view dimensions for detection
- **aim_fov_x/aim_fov_y**: Aiming field of view dimensions
- **fps**: Target framerate for detection
- **auto_detect_resolution**: Automatically detect screen resolution
- **resolution_x/resolution_y**: Manual resolution settings
- **min_target_area**: Minimum target area for detection

### 🎯 [aim]
```ini
offset = 0
smooth = 0.2
speed = 1
y_speed = 1
aim_height = 0.87
```

- **offset**: Aim offset adjustment
- **smooth**: Aim smoothing factor (0.1-1.0)
- **speed**: Horizontal aim speed multiplier
- **y_speed**: Vertical aim speed multiplier
- **aim_height**: Target aim height percentage (0.0-1.0)

### 🔄 [recoil]
```ini
mode = move
recoil_x = 0.8
recoil_y = 1.8
max_offset = 80
recover = 0.85
```

- **mode**: Recoil compensation mode
- **recoil_x**: Horizontal recoil compensation strength
- **recoil_y**: Vertical recoil compensation strength
- **max_offset**: Maximum recoil offset
- **recover**: Recoil recovery factor

### ⚡ [trigger]
```ini
trigger_delay = 1
trigger_randomization = 1
trigger_threshold = 3
```

- **trigger_delay**: Delay before triggering (ms)
- **trigger_randomization**: Random delay variance
- **trigger_threshold**: Sensitivity threshold for triggering

### 🔥 [rapid_fire]
```ini
target_cps = 15
```

- **target_cps**: Target clicks per second

### ⌨️ [key_binds]
```ini
key_reload_config = 0x70    # F1
key_toggle_aim = 0x71       # F2
key_toggle_recoil = 0x72    # F3
key_exit = 0x73             # F4
key_trigger = 0x06          # Right Click
key_rapid_fire = 0x05       # X1 Mouse Button
aim_keys = 0x01, 0x02       # Left Click, Right Click
```

<details>
<summary>🔍 <strong>Key Code Reference</strong></summary>

- `0x70` = F1
- `0x71` = F2
- `0x72` = F3
- `0x73` = F4
- `0x01` = Left Mouse Button
- `0x02` = Right Mouse Button
- `0x05` = X1 Mouse Button
- `0x06` = X2 Mouse Button

</details>

---

## 🚀 Usage

### 🎮 Starting the Application
1. ▶️ Run `Loader.py` (or the compiled executable)
2. 🖥️ The console will display the ValoAim interface
3. 🔐 License verification will occur automatically
4. ⌨️ Features can be toggled using the configured hotkeys

### 🎛️ Interface Overview
```
╔══════════════════════════════════════════════════════════╗
║     __     ___    _     ___    _    ___ __  __           ║
║     \ \   / / \  | |   / _ \  / \  |_ _|  \/  |          ║
║      \ \ / / _ \ | |  | | | |/ _ \  | || |\/| |          ║
║       \ V / ___ \| |__| |_| / ___ \ | || |  | |          ║
║        \_/_/   \_\_____\___/_/   \_\___|_|  |_|          ║
║                           V1.5                           ║
╠══════════════════════════════════════════════════════════╣
║  Expires: 2024-12-31                                     ║
║  Time left: 30 days                                      ║
╠──────────────────────────────────────────────────────────╣
║  Connection: Connected                                   ║
║  Aimbot:    ON (F2)                                      ║
║  Recoil:    OFF (F3)                                     ║
║  Exit:      (F4)                                         ║
╚══════════════════════════════════════════════════════════╝
```

### 📊 Real-time Status
- 🔌 **Connection**: Shows hardware connection status
- 🎯 **Aimbot**: Current aim assistance state
- 🔄 **Recoil**: Current recoil compensation state
- 🔐 **License Info**: Shows expiration date and remaining time

---

## ⌨️ Key Bindings

| Key | Function | Description |
|-----|----------|-------------|
| 🔄 F1 | Reload Config | Reload configuration from config.ini |
| 🎯 F2 | Toggle Aim | Enable/disable aim assistance |
| 🔄 F3 | Toggle Recoil | Enable/disable recoil compensation |
| ❌ F4 | Exit | Close the application |
| 🖱️ Right Click | Trigger | Activate trigger bot |
| 🔥 X1 Mouse | Rapid Fire | Activate rapid fire |
| 🖱️ Left/Right Click | Aim Keys | Mouse buttons for aim activation |

---

## 🔍 Troubleshooting

### ⚠️ Common Issues

<details>
<summary>📄 <strong>Config file not found</strong></summary>

- Ensure `config.ini` is in the same directory as the executable
- Check file permissions
- Verify the file is not corrupted

</details>

<details>
<summary>🔌 <strong>Connection issues</strong></summary>

- Verify COM port is correct and available
- Check if device is properly connected
- Try different COM ports (COM1, COM2, COM3, etc.)

</details>

<details>
<summary>🎯 <strong>Detection not working</strong></summary>

- Adjust color ranges in the screen section
- Modify detection threshold values
- Check resolution settings
- Ensure adequate lighting conditions

</details>

<details>
<summary>⚡ <strong>Performance issues</strong></summary>

- Lower the FPS setting
- Reduce FOV dimensions
- Adjust detection threshold
- Close unnecessary applications

</details>

### 💡 Configuration Tips

> **🎨 Color Detection**: Use a color picker tool to find the exact HSV values for your targets
> 
> **🎯 Smooth Aiming**: Start with higher smooth values (0.5-0.8) and gradually decrease
> 
> **🔄 Recoil Patterns**: Test different weapons and adjust recoil values accordingly
> 
> **📏 FOV Settings**: Smaller FOV = better performance, larger FOV = wider detection

---

## 🆘 Support

For technical support or feature requests, please ensure you have:
- ✅ Valid license key
- ✅ Current version (V1.5)
- ✅ Detailed description of the issue
- ✅ Your configuration file (with license key removed)

---

## ⚖️ Legal Notice

> **⚠️ Important**: This software is intended for educational and testing purposes only. Users are responsible for complying with all applicable laws and terms of service for any games or applications used with this software.

---

<div align="center">

### 🌟 Made with ❤️ by ValoAim Team

*Happy aiming! 🎯*

</div>
