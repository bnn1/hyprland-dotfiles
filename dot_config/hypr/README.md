# Hyprland Configuration with chezmoi

This is a modular, power-user Hyprland configuration managed with chezmoi.

## Structure

```
~/.config/hypr/
├── hyprland.conf          # Main config (sources all modules)
├── hyprpaper.conf         # Wallpaper configuration
├── hypridle.conf          # Idle management configuration
└── configs/               # Modular configuration files
    ├── monitors.conf      # Monitor setup (templated)
    ├── environment.conf   # Environment variables
    ├── autostart.conf     # Startup applications
    ├── input.conf         # Keyboard/mouse/touchpad settings (templated)
    ├── looks.conf         # Theme, animations, layouts (templated)
    ├── keybinds.conf      # All keybindings (templated)
    └── windowrules.conf   # Window and workspace rules
```

## Customization

All machine-specific settings are managed through `~/.config/chezmoi/chezmoi.toml`.

Edit this file to customize:
- Terminal, file manager, launcher applications
- Monitor configurations
- Theme colors and dimensions
- Input device settings
- Keyboard layout

After editing, run:
```bash
chezmoi apply
```

## Key Bindings

**Main Modifier:** `Super` (Windows key)

### Basic
- `Super + Q` - Open terminal
- `Super + C` - Close window
- `Super + M` - Exit Hyprland
- `Super + E` - File manager
- `Super + R` - App launcher
- `Super + V` - Toggle floating
- `Super + F` - Fullscreen
- `Super + L` - Lock screen

### Screenshots
- `Super + Print` - Screenshot selection to clipboard
- `Print` - Screenshot all to clipboard
- `Super + Shift + S` - Screenshot selection to file
- `Shift + Print` - Screenshot all to file

### Window Management
- `Super + Arrow Keys` - Move focus
- `Super + H/J/K/L` - Move focus (vim keys)
- `Super + Shift + Arrow/HJKL` - Move window
- `Super + Ctrl + Arrow Keys` - Resize window

### Workspaces
- `Super + [1-9,0]` - Switch to workspace
- `Super + Shift + [1-9,0]` - Move window to workspace
- `Super + Alt + [1-9,0]` - Move window silently
- `Super + S` - Toggle scratchpad
- `Super + [/]` - Next/previous workspace

### Utilities
- `Super + .` - Clipboard history
- `Super + Shift + C` - Color picker

## Installed Utilities

- **mako** - Notification daemon
- **waybar** - Status bar
- **wofi** - Application launcher
- **hyprpaper** - Wallpaper manager
- **hypridle** - Idle management
- **hyprlock** - Screen locker
- **hyprsunset** - Blue light filter
- **hyprpicker** - Color picker
- **cliphist** - Clipboard manager
- **grim/slurp** - Screenshot tools

## Wallpaper Setup

1. Create wallpaper directory:
   ```bash
   mkdir -p ~/Pictures/wallpapers
   ```

2. Add your wallpaper (rename or adjust path in `hyprpaper.conf`):
   ```bash
   cp /path/to/wallpaper.jpg ~/Pictures/wallpapers/default.jpg
   ```

3. Reload hyprpaper:
   ```bash
   killall hyprpaper; hyprpaper &
   ```

## Managing with chezmoi

```bash
# Check status
chezmoi status

# Preview changes
chezmoi diff

# Apply changes
chezmoi apply

# Edit files in chezmoi
chezmoi edit ~/.config/hypr/hyprland.conf

# Add new files to chezmoi
chezmoi add ~/.config/hypr/somefile.conf

# Update repository
cd ~/.local/share/chezmoi
git add .
git commit -m "Update config"
git push
```

## Reload Configuration

Hyprland automatically reloads when you save config files. For manual reload:
```bash
hyprctl reload
```

## Resources

- [Hyprland Wiki](https://wiki.hypr.land/)
- [chezmoi Documentation](https://www.chezmoi.io/)
- [Awesome Hyprland](https://github.com/hyprland-community/awesome-hyprland)
