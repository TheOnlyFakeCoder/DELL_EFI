# Dell [Your Laptop Model, e.g., Latitude 5490] Hackintosh

An OpenCore-based EFI repository to run macOS (Ventura/Sonoma) on a Dell [Your Laptop Model] laptop. This configuration is optimized for daily driver stability, power efficiency, and performance.

## Hardware Specifications

| Component      | Specification                    | Status                                         |
| :------------- | :------------------------------- | :--------------------------------------------- |
| **CPU**        | Intel Core [e.g., i5-8250U]      | Works (with full power management)             |
| **GPU**        | Intel UHD Graphics [e.g., 620]   | Works (Full QE/CI Acceleration)                |
| **RAM**        | [e.g., 8GB/16GB] DDR4            | Works                                          |
| **Audio**      | Realtek ALC [e.g., 256]          | Works (Layout ID: [e.g., 21 or 13])            |
| **Ethernet**   | Intel Mausi                      | Works                                          |
| **Wi-Fi / BT** | Qualcomm/Atheros [e.g., QCA6174] | **Incompatible** (Use Ethernet during install) |
| **Storage**    | ADATA 256GB SSD                  | Works (AHCI Mode required)                     |
| **Display**    | [e.g., 14" FHD 1920x1080]        | Works                                          |
| **Touchpad**   | I2C/PS2 Touchpad                 | Works (with macOS multi-touch gestures)        |

---

## Status & Features

### Working ✅

- [x] **Graphics:** Full Intel UHD acceleration with smooth animations (Metal / QE/CI).
- [x] **CPU Power Management:** Proper frequency stepping via VirtualSMC.
- [x] **Audio & Jack Detection:** Clean audio from speakers, headphones, and working microphone.
- [x] **Ethernet:** Plug-and-play wired internet connection via `IntelMausi.kext`.
- [x] **Touchpad & Keyboard:** Smooth tracking, multi-touch gestures, and brightness/volume hotkeys.
- [x] **USB Ports:** All ports mapped correctly (USB 3.0 speeds and Type-C video output/data).
- [x] **Sleep & Wake:** Native sleep/wake functionality (clamshell sleep works).
- [x] **Battery Status:** Accurate percentage readings and time estimates.

### Not Working / In Progress ⚠️

- [ ] **Wi-Fi & Bluetooth:** The internal Qualcomm card is natively unsupported by modern macOS. A hardware swap to an Intel or Broadcom card is highly recommended for wireless features.

---

## Repository Structure

```text
EFI/
├── BOOT/
│   └── BOOTx64.efi
└── OC/
    ├── ACPI/              # Custom DSDT/SSDT patches (Battery, I2C, XOSI)
    ├── Drivers/           # OpenCore runtime drivers (OpenRuntime, HfsPlus)
    ├── Kexts/             # Device drivers (VirtualSMC, Lilu, IntelMausi, etc.)
    ├── Tools/             # OpenCore debug tools (OpenShell)
    └── config.plist       # Main configuration file (Intel Laptop Template)
```
