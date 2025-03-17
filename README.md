# FlipMouse

This is a magisk module and requires a rooted android phone with magisk installed.

A virtual mouse driver for the TCL FLIP 2 (and other compatible devices) that allows you to transform your keypad into a fully functional mouse.

## Overview

FlipMouse enables a virtual mouse mode that can be toggled on and off, allowing you to control your cursor with the keypad or keyboard directional buttons. This is especially useful for devices like the TCL FLIP 2 where mouse functionality might be limited or non-existent.

## Features

- 🖱️ Toggle virtual mouse mode on/off with a dedicated key
- ⬆️ Navigate using arrow keys or keypad
- 🖱️ Left click and drag functionality
- 🔄 Scroll up/down support
- ⚡ Adjustable mouse speed
- 🔄 Works with both TCL FLIP 2 keypad and standard keyboards

## Installation

### ADB Shell (Recommended)

1. Download the FlipMouse.zip from the releases page.
2. `adb push /path/to/FlipMouse.zip /sdcard/Download`
3. `adb shell su -c "magisk --install-module /sdcard/Download/FlipMouse.zip"`

### From the device

1. Download the FlipMouse.zip from the releases page to the phone.
2. Open Magisk and navigate to modules
3. Install from file, and reboot phone.

## Key Bindings

| Key                        | Function                            |
| -------------------------- | ----------------------------------- |
| Star Key (contacts) or F12 | Toggle mouse mode on/off            |
| Hold Star Key              | Open contacts (default star action) |
| Arrow keys                 | Move cursor                         |
| Enter Key                  | Mouse click                         |
| Top Right Soft Key         | Toggle drag mode                    |
| Top Left Soft Key          | Scroll up                           |
| Phone Key                  | Scroll down                         |
| Volume Up                  | Increase mouse speed                |
| Volume Down                | Decrease mouse speed                |

## Building from source

### Requirements

- Linux-based system
- libevdev library
- Root permissions (to access input devices)

1. Clone this repository:

   ```
   git clone https://github.com/tylerboni/flipmouse.git
   cd flipmouse
   ```

2. Install dependencies:

   ```
   # Debian/Ubuntu
   sudo apt-get install libevdev-dev
   ```

   ```
   # Arch
   sudo pacman -S libevdev
   ```

3. Compile the code:

   ```
   # Debug flag builds for linux desktop and runs
   ./make-mouse [--debug]
   ```

4. To install:
   ```
   ./install
   ```

## How It Works

FlipMouse works by:

1. Finding and grabbing supported input devices
2. Creating a virtual mouse device using libevdev
3. Intercepting key events and converting them to mouse movements when in mouse mode
4. Passing through normal key events when not in mouse mode

## Supported Devices

Currently supported devices:

- TCL FLIP 2
- AT Translated Set 2 keyboard (standard laptop keyboards)

## License

[MIT License](LICENSE)

## Author

Tyler Boni

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

<a href="https://www.buymeacoffee.com/tylerboni" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
