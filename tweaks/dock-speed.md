# Dock Speed

Hide/show the Dock with **⌥⌘D**. The default reappear animation is slow; change it with:

```bash
# Instant (no animation)
defaults write com.apple.dock autohide-time-modifier -int 0; killall Dock

# Split-second (value = seconds the animation takes)
defaults write com.apple.dock autohide-time-modifier -float 0.15; killall Dock

# Revert to default
defaults delete com.apple.dock autohide-time-modifier; killall Dock
```

---
[⬅️ Back to README](../README.md#system-tweaks)
