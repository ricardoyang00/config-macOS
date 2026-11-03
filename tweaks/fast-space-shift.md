# Fast Space Shift

Removes the slow animation when switching Spaces, using [yabai](https://github.com/koekeishiya/yabai) + [skhd](https://github.com/koekeishiya/skhd). Based on [this guide](https://text.is/yabai-guide).

**1. Disable SIP.** Shut down, then turn the Mac on holding the power button until *Startup Options* appears. Open *Options → Utilities → Terminal* and run:
```bash
csrutil disable
```
Reboot, then check with `csrutil status`. It should return `System Integrity Protection status: disabled.`

> On Apple Silicon, yabai's scripting addition also needs `sudo nvram boot-args=-arm64e_preview_abi` (then reboot).

**2. Install** (requires [Homebrew](https://brew.sh)):
```bash
brew install koekeishiya/formulae/yabai jq koekeishiya/formulae/skhd
sudo yabai --load-sa
```

**3. Configure:**
```bash
mkdir -p ~/.config/yabai ~/.config/skhd
touch ~/.config/yabai/yabairc ~/.config/skhd/skhdrc
chmod +x ~/.config/yabai/yabairc ~/.config/skhd/skhdrc
```
Add the shortcuts to `~/.config/skhd/skhdrc` (`ctrl` and/or `alt` + arrows):
```
alt - right : yabai -m space --focus next
alt - left : yabai -m space --focus prev
ctrl - right : yabai -m space --focus next
ctrl - left : yabai -m space --focus prev
```
Reboot.

**4. Start the services:**
```bash
sudo yabai --load-sa
yabai --start-service
skhd --start-service
```

---
[⬅️ Back to README](../README.md#system-tweaks)
