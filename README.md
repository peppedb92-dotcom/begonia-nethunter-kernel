# Begonia NetHunter Kernel Builder

Kali NetHunter kernel for Xiaomi Redmi Note 8 Pro (begonia) based on Android 14 R-OSS kernel tree.

## How to use

### Prerequisites
- A GitHub account
- Git installed on your PC

### Setup

1. **Create a new GitHub repository** (e.g., `begonia-nethunter-kernel`)
   - Go to https://github.com/new
   - Name: `begonia-nethunter-kernel`
   - Public or Private (public recommended for Actions)

2. **Push these files to your repo:**
   ```bash
   cd C:\Users\JDB\Desktop\begonia-nethunter-kernel
   git init
   git add .
   git commit -m "Initial commit: NetHunter kernel builder for begonia"
   git remote add origin https://github.com/YOUR_USERNAME/begonia-nethunter-kernel.git
   git branch -M main
   git push -u origin main
   ```

3. **Run the workflow:**
   - Go to your repo on GitHub
   - Click **Actions** tab
   - Click **Build Begonia NetHunter Kernel** workflow
   - Click **Run workflow**
   - Default inputs should work (kernel from `xiaomi-begonia-dev/android_kernel_xiaomi_mt6785`, branch `fourteen`)
   - Click **Run**

4. **Wait for the build** (~30-60 minutes)

5. **Download the artifact:**
   - When done, click on the completed workflow run
   - Under **Artifacts**, download `begonia-NetHunter-Kernel-A14.zip`

### Flash

1. Boot into custom recovery (BRP/TWRP)
2. Flash `begonia-NetHunter-Kernel-A14.zip`
3. Reboot
4. Install NetHunter app from https://www.kali.org/get-kali/#kali-mobile
5. Open NetHunter app → it should detect the kernel

## Features
- HID keyboard/mouse attacks (USB gadget)
- External USB Wi-Fi adapter support (RTL8187, etc.)
- MAC80211/CFG80211 for monitor mode with external adapters
- Bluetooth HID attacks
- USB serial adapters (FTDI, PL2303, CP210X)
- TTL target (ip table modification)
- Full NetHunter chroot

## Customizing
Edit `.github/workflows/build-begonia-nethunter.yml` to:
- Change kernel source repo/branch
- Add more NetHunter config options
- Add KernelSU support
