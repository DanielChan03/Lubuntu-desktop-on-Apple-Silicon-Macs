# 🧩 Full Guide: Install Lubuntu on Mac using UTM

This guide walks you through:
1. Installing UTM
2. Installing Ubuntu in a VM
3. Converting Ubuntu → Lubuntu
4. Cleaning up the system

---

# 📌 Requirements

- Mac (Intel or Apple Silicon)
- At least:
  - 4GB RAM (8GB recommended)
  - 20GB storage
- Internet connection

---

# 🚀 Step 1: Install UTM

1. Download UTM from:
   https://mac.getutm.app/
2. Install and open UTM

---

# 💿 Step 2: Download Ubuntu ISO

1. Go to:
   https://ubuntu.com/download/desktop
2. Download the latest Ubuntu Desktop ISO  
   Example:
   Ubuntu 25.10 (ARM 64-bit architecture)
   https://cdimage.ubuntu.com/releases/25.10/release/ubuntu-25.10-desktop-arm64.iso


---

# 🖥️ Step 3: Create Virtual Machine in UTM

1. Open UTM → Click **Create New**
2. Choose:
- **Virtualize** (Apple Silicon - recommended)
- **Emulate** (if using x86 ISO on ARM)

3. Select:
- **Linux**

4. Boot ISO Image:
- Select your Ubuntu ISO file

---

## ⚙️ Recommended Settings

- Memory: **4GB (4096 MB)**
- CPU: **2–4 cores**
- Storage: **20GB+**
- Display:
- Use **VirtIO-GPU**

---

# 🧩 Step 4: Install Ubuntu

1. Start VM
2. Select:
**Install Ubuntu**
3. Follow installer:
- Language
- Keyboard
- Normal installation
- Erase disk (VM only, safe)
- Create username/password

4. Wait for installation to complete

---

# 🔁 Step 5: First Boot Setup

After installation:
- Restart VM
- Remove ISO if prompted
- Log into Ubuntu

---

# 🚀 Step 6: Convert Ubuntu → Lubuntu

Open Terminal and run:

```bash
sudo apt update && sudo apt upgrade -y && sudo apt install lubuntu-desktop sddm -y && echo "/usr/bin/sddm" | sudo tee /etc/X11/default-display-manager && sudo reboot

✅ What this does
Installs Lubuntu (LXQt desktop)
Installs SDDM display manager
Sets SDDM as default
Reboots system

---

# 🔐 Step 7: Select Lubuntu Session

After reboot:

At login screen
Click ⚙️ (settings icon)
Select Lubuntu
Log in

---

# ✅ Step 8: Verify Installation

Run:

echo $XDG_CURRENT_DESKTOP

Expected output:

LXQt

---

# 🔒 Step 9: Set Lubuntu as Default
echo -e "[General]\nSession=Lubuntu" > ~/.dmrc
chmod 644 ~/.dmrc
🧹 Step 10: Remove Ubuntu Desktop (Optional)

⚠️ Only after confirming Lubuntu works

sudo apt remove ubuntu-desktop gnome-shell -y
sudo apt autoremove -y
⚡ Optional: Ultra-Light Setup (Better Performance)

Instead of full Lubuntu, install minimal LXQt:

sudo apt update && sudo apt install lxqt-core sddm -y && echo "/usr/bin/sddm" | sudo tee /et
  
