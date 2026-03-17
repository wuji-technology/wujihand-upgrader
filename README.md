# wujihand-upgrader

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Release](https://img.shields.io/github/v/release/wuji-technology/wujihand-upgrader)](https://github.com/wuji-technology/wujihand-upgrader/releases)

Wuji Hand Upgrader: firmware upgrade tool for Wuji Hand.

## Table of Contents

- [Usage](#usage)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running](#running)
- [Contact](#contact)

## Usage

### Prerequisites

- **OS**: Ubuntu 22.04 LTS / Ubuntu 24.04 LTS
- **Architecture**: x86_64 (AMD64)

### Installation

#### Debian Package (.deb)

Debian packages provide system-level installation with automatic permission configuration.

#### Download

Download the latest .deb package:
- GitHub Releases: [https://github.com/wuji-technology/wujihand-upgrader/releases](https://github.com/wuji-technology/wujihand-upgrader/releases)

#### Install

Install the application using apt. Replace `<downloaded-package-name>` with the actual package name.

```bash
sudo apt install ./<downloaded-package-name>.deb
# If dependency issues occur
sudo apt-get install -f
```

#### Permission Configuration

After installation, the system will automatically:
- Configure serial port access permissions
- Add user to required groups
- Set up hardware access permissions

#### Uninstall

```bash
sudo apt remove wujihand-upgrader
```

### Running

Click the "WUJI" app icon on your desktop.

**Note**: First run may take longer to extract and initialize the application.

#### Upgrade Procedure

Firmware upgrade requires the following sequence:

1. Ensure the hand is **powered off**, then open Wuji Hand Upgrader application
2. Connect the hand to PC via USB, then power on the hand
3. The application will auto-connect to the bootloader
4. Proceed with firmware upgrade

**Note**: If the application shows "not in bootloader mode", power cycle the hand and retry.

## Troubleshooting

### Window Not Appearing (GBM Buffer Error)

**Symptom**: After installation, clicking the desktop icon shows an icon in the sidebar but the upgrader window never appears. 

Running from terminal shows:

> Failed to create GBM buffer of size 1280x720: Permission denied

**Cause**: This is likely related to the NVIDIA driver not having
  DRM kernel mode setting enabled. See [dioxus#1909](https://github.com/DioxusLabs/dioxus/issues/1909#issuecomment-1974930010) for details.
  
**Solution**:
  1. Check if modesetting is enabled:

     `cat /sys/module/nvidia_drm/parameters/modeset`

  2. If the output is `N`, enable it:

     `echo options nvidia_drm modeset=1 | sudo tee /etc/modprobe.d/nvidia_drm.conf`

  3. Restart your computer.

## Contact

For any questions, please contact [support@wuji.tech](mailto:support@wuji.tech).
