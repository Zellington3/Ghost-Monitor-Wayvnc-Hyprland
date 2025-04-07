# 👻 WayVNC Ghost Monitor for Hyprland

> ⚠️ **Disclaimer:** This is **not an official WayVNC package**.  
> It’s a community-created script for integrating WayVNC with Hyprland using a headless (ghost) monitor setup.

Create a **ghost monitor** (a virtual headless output) in [Hyprland](https://github.com/hyprwm/Hyprland) and stream it wirelessly using [WayVNC](https://github.com/any1/wayvnc).

👻 **Seamlessly turn any laptop or PC** with a VNC viewer (like TigerVNC) into a **wireless display** for your Hyprland setup — with **automatic cleanup** when you're done!

---

## ✨ Features

- 🖥️ Dynamically creates a **virtual headless monitor**
- 🔀 Assigns a workspace to the ghost monitor
- 🧼 Automatically **cleans up** on exit (moves workspace back and stops WayVNC)
- 🧠 Keeps your **real monitor focused**
- 🌐 Works with **any VNC viewer** like TigerVNC or RealVNC

---

## ⚙️ Requirements

- [Hyprland](https://github.com/hyprwm/Hyprland) (version 0.48.0 or later)
- [WayVNC](https://github.com/any1/wayvnc) (version 0.9.1 or later)
- A POSIX-compatible shell like `bash` or `zsh`  
  > 📝 This script is written in `zsh`, but it works in `bash` too — just update the shebang (`#!/usr/bin/env bash`) if needed.

### 📦 WayVNC Dependencies

Ensure the following packages are installed (package names may vary by distribution):

- `wayland`
- `pixman`
- `glibc`
- `jansson`
- `libxkbcommon`
- `libdrm`
- `libxcb`
- `xcb-util`
- `neatvnc`
- `aml`
- `pam` (optional, for authentication)

You can install them using your distro's package manager (e.g., `pacman`, `apt`, `dnf`) or build from source as outlined in the [WayVNC GitHub repo](https://github.com/any1/wayvnc#dependencies).

---

### 🖥️ Platform Compatibility

This script is designed **specifically for Linux systems running Hyprland on Wayland** to allow them to connect to **any system that can run a compatible VNC viewer**. It will **not work on**:

- macOS or Windows
- X11-based desktop environments
- Other compositors like GNOME, KDE Plasma, or Sway

It relies on `hyprctl`, which is exclusive to Hyprland, and WayVNC, which only runs on Wayland.

---

## 🛠️ Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/wayvnc-hyprland-ghost-monitor.git
   cd wayvnc-hyprland-ghost-monitor
   ```

2. **Make the script executable:**
   ```bash
   chmod +x wayvnc-ghost-monitor.sh
   ```

3. **Configure the script as needed:**
   Edit the following variables at the top of the script to match your setup:
   ```sh
   VIRTUAL_MONITOR="HEADLESS-2"   # Name of the ghost monitor
   VIRTUAL_WORKSPACE=3            # Workspace to assign to the ghost monitor
   REAL_MONITOR="DP-2"            # Your real physical monitor
   ```

   > ⚠️ **NOTE:** If you already use 3 or more workspaces or monitors by default, consider setting `VIRTUAL_WORKSPACE` to a higher number (e.g., 10 or 11) to avoid conflicts or unexpected behavior.

4. **Hyprland Configuration (if needed):**

   If you're using a **static monitor setup**, you'll need to manually define the ghost monitor:

   - **Regular Hyprland:** Add the following line to the `monitors` section of `~/.config/hypr/hyprland.conf`
   - **HyDE Hyprland:** Add the line to `~/.config/hypr/monitors.conf`

   ```ini
   monitor=HEADLESS-2,1920x1080@60,0x0,1
   ```

   > ⚠️ **NOTE:** While this script attempts to dynamically create a headless monitor using `hyprctl output create`, **some setups (especially with HyDE Hyprland or stricter monitor management)** may still require the monitor to be declared manually for consistent behavior.
   >
   > We **intentionally omitted automatic config file editing** from the script to prevent potential issues with your Hyprland setup. It's safer to manually add the entry and back up your configuration beforehand.

   ✅ If you're using dynamic monitor creation in regular Hyprland and don’t have a static layout, this step may not be necessary.

   🔧 For GUI-based monitor management, consider using [ngx-displays](https://github.com/Aylur/ngx-displays).

---

## 🚀 Usage

1. **Run the script:**
   ```bash
   ./wayvnc-ghost-monitor.sh
   ```

2. **Connect from another device using a VNC viewer:**
   ```bash
   vncviewer your-hyprland-ip:5900
   ```

   > 💡 You can use any VNC viewer like [TigerVNC](https://tigervnc.org/) or [RealVNC Viewer](https://www.realvnc.com/en/connect/download/viewer/).

---

## 🧼 Cleanup on Exit

When you press `Ctrl+C` or the script ends:
- WayVNC is stopped
- The workspace is moved back to your real monitor
- Monitor focus is restored

No manual cleanup required!

---

## 🧪 Tested With

- **Hyprland:** version 0.48.0 (released March 2025)  
- **HyDE Hyprland:** latest version as of March 2025  
- **WayVNC:** version 0.9.1 (released November 2024)  
- **TigerVNC:** version 1.15.0 (released February 2025)  
- **RealVNC Viewer:** version 7.12.1 (released December 2024)  
- 🏹 **Operating System:** Arch Linux with Zsh and Bash

---

## 🙌 Acknowledgments

Thanks to the Hyprland, WayVNC, and Linux desktop communities for making modern, dynamic workflows possible.
```

---

Let me know if you'd like me to generate this as a downloadable `.md` file or create a GitHub `README.md` layout preview for you!Perfect addition! I've seamlessly plugged your improved **Platform Compatibility** section into the full README below — everything is polished, clear, and user-friendly:

---

```markdown
# 👻 WayVNC Ghost Monitor for Hyprland

> ⚠️ **Disclaimer:** This is **not an official WayVNC package**.  
> It’s a community-created script for integrating WayVNC with Hyprland using a headless (ghost) monitor setup.

Create a **ghost monitor** (a virtual headless output) in [Hyprland](https://github.com/hyprwm/Hyprland) and stream it wirelessly using [WayVNC](https://github.com/any1/wayvnc).

👻 **Seamlessly turn any laptop or PC** with a VNC viewer (like TigerVNC) into a **wireless display** for your Hyprland setup — with **automatic cleanup** when you're done!

---

## ✨ Features

- 🖥️ Dynamically creates a **virtual headless monitor**
- 🔀 Assigns a workspace to the ghost monitor
- 🧼 Automatically **cleans up** on exit (moves workspace back and stops WayVNC)
- 🧠 Keeps your **real monitor focused**
- 🌐 Works with **any VNC viewer** like TigerVNC or RealVNC

---

## ⚙️ Requirements

- [Hyprland](https://github.com/hyprwm/Hyprland) (version 0.48.0 or later)
- [WayVNC](https://github.com/any1/wayvnc) (version 0.9.1 or later)
- A POSIX-compatible shell like `bash` or `zsh`  
  > 📝 This script is written in `zsh`, but it works in `bash` too — just update the shebang (`#!/usr/bin/env bash`) if needed.

### 📦 WayVNC Dependencies

Ensure the following packages are installed (package names may vary by distribution):

- `wayland`
- `pixman`
- `glibc`
- `jansson`
- `libxkbcommon`
- `libdrm`
- `libxcb`
- `xcb-util`
- `neatvnc`
- `aml`
- `pam` (optional, for authentication)

You can install them using your distro's package manager (e.g., `pacman`, `apt`, `dnf`) or build from source as outlined in the [WayVNC GitHub repo](https://github.com/any1/wayvnc#dependencies).

---

### 🖥️ Platform Compatibility

This script is designed **specifically for Linux systems running Hyprland on Wayland** to allow them to connect to **any system that can run a compatible VNC viewer**. It will **not work on**:

- macOS or Windows
- X11-based desktop environments
- Other compositors like GNOME, KDE Plasma, or Sway

It relies on `hyprctl`, which is exclusive to Hyprland, and WayVNC, which only runs on Wayland.

---

## 🛠️ Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/wayvnc-hyprland-ghost-monitor.git
   cd wayvnc-hyprland-ghost-monitor
   ```

2. **Make the script executable:**
   ```bash
   chmod +x wayvnc-ghost-monitor.sh
   ```

3. **Configure the script as needed:**
   Edit the following variables at the top of the script to match your setup:
   ```sh
   VIRTUAL_MONITOR="HEADLESS-2"   # Name of the ghost monitor
   VIRTUAL_WORKSPACE=3            # Workspace to assign to the ghost monitor
   REAL_MONITOR="DP-2"            # Your real physical monitor
   ```

   > ⚠️ **NOTE:** If you already use 3 or more workspaces or monitors by default, consider setting `VIRTUAL_WORKSPACE` to a higher number (e.g., 10 or 11) to avoid conflicts or unexpected behavior.

4. **Hyprland Configuration (if needed):**

   If you're using a **static monitor setup**, you'll need to manually define the ghost monitor:

   - **Regular Hyprland:** Add the following line to the `monitors` section of `~/.config/hypr/hyprland.conf`
   - **HyDE Hyprland:** Add the line to `~/.config/hypr/monitors.conf`

   ```ini
   monitor=HEADLESS-2,1920x1080@60,0x0,1
   ```

   > ⚠️ **NOTE:** While this script attempts to dynamically create a headless monitor using `hyprctl output create`, **some setups (especially with HyDE Hyprland or stricter monitor management)** may still require the monitor to be declared manually for consistent behavior.
   >
   > We **intentionally omitted automatic config file editing** from the script to prevent potential issues with your Hyprland setup. It's safer to manually add the entry and back up your configuration beforehand.

   ✅ If you're using dynamic monitor creation in regular Hyprland and don’t have a static layout, this step may not be necessary.

   🔧 For GUI-based monitor management, consider using [ngx-displays](https://github.com/Aylur/ngx-displays).

---

## 🚀 Usage

1. **Run the script:**
   ```bash
   ./wayvnc-ghost-monitor.sh
   ```

2. **Connect from another device using a VNC viewer:**
   ```bash
   vncviewer your-hyprland-ip:5900
   ```

   > 💡 You can use any VNC viewer like [TigerVNC](https://tigervnc.org/) or [RealVNC Viewer](https://www.realvnc.com/en/connect/download/viewer/).

---

## 🧼 Cleanup on Exit

When you press `Ctrl+C` or the script ends:
- WayVNC is stopped
- The workspace is moved back to your real monitor
- Monitor focus is restored

No manual cleanup required!

---

## 🧪 Tested With

- **Hyprland:** version 0.48.0 (released March 2025)  
- **HyDE Hyprland:** latest version as of March 2025  
- **WayVNC:** version 0.9.1 (released November 2024)  
- **TigerVNC:** version 1.15.0 (released February 2025)  
- **RealVNC Viewer:** version 7.12.1 (released December 2024)  
- **Operating System:** Arch Linux with Zsh and Bash

---

## 🙌 Acknowledgments

Thanks to the Hyprland, WayVNC, and Linux desktop communities for making modern, dynamic workflows possible.
