# AeroSpace Configuration

## Installation

1. Install AeroSpace:
```bash
brew install --cask nikitabobko/tap/aerospace
```

2. Install dependencies:

refer to https://github.com/ripple0328/sketchybar-config 
```bash
# SketchyBar (menu bar integration)
brew install --cask sketchybar
```

3. Copy configuration files to AeroSpace config directory:
```bash
git clone https://github.com/ripple0328/aerospace-config.git ~/.config/aerospace
```

4. Grant necessary permissions:
   - System Preferences → Privacy & Security → Accessibility → Add AeroSpace
   - System Preferences → Privacy & Security → Screen Recording → Add AeroSpace (if using screenshots)

5. Start AeroSpace:
```bash
aerospace --config-path ~/.config/aerospace/aerospace.toml
```

## 🚀 Hybrid Mode System

### Core Philosophy
- **Frequent operations (80%)**: Direct access in main mode with clean prefixes
- **Advanced operations (20%)**: Organized in specialized modes
- **Best of both worlds**: Speed for daily workflows + organization for complex operations

### Mode Overview
- **Main Mode**: Window focus/movement, workspace switching, move-to-workspace
- **alt-ctrl-w** = **Window** mode (resize, join, monitor, close operations)
- **alt-ctrl-s** = **Space** mode (move-and-follow, navigation, monitor ops)
- **alt-ctrl-l** = **Layout** mode (layouts, containers)
- **alt-ctrl-a** = **App** mode (application launching)
- **alt-ctrl-m** = **Maintenance** mode (system utilities, config, themes)

### Mode Navigation
- **Single exit**: `esc` always returns to main mode
- **Cross-mode switching**: Jump between modes without returning to main
- **No self-switching**: Can't switch to the mode you're already in

## 🎯 Workspace Organization

### 7 Configured Workspaces
- **1-3**: Project workspaces (organize windows by project)
- **A**: AI tools (ChatGPT, Google Gemini, LM Studio)
- **B**: Browsers (Chrome, Safari) 
- **C**: Calendar
- **E**: Editors (Zed, Emacs, Cursor)
- **T**: Terminals (Warp, Allactty)
- **M**: Messages (Mail, Google Chat, WeChat)

## ⌨️ Keybinding Reference

### Main Mode (Always Active) - Frequent Operations

#### Window Operations (Immediate Access)
```bash
# Window focus (vim-style) - MOST FREQUENT
alt-h/j/k/l                    # Focus left/down/up/right
alt-left/right/up/down         # Alternative arrow key focus

# Window movement - VERY FREQUENT  
alt-shift-h/j/k/l              # Move window left/down/up/right
alt-shift-left/right/up/down   # Alternative arrow key movement
```

#### Workspace Operations (Immediate Access)
```bash
# Workspace switching - VERY FREQUENT
alt-tab                        # Back-and-forth between recent workspaces
alt-1/2/3                      # Switch to numbered workspaces  
alt-a/b/c/e/t/m                # Switch to semantic workspaces

# Move window to workspace - FREQUENT
cmd-alt-1/2/3                  # Move window to numbered workspace
cmd-alt-a/b/c/e/t/m            # Move window to semantic workspace
```

#### Essential Shortcuts
```bash
# Mode switching
alt-ctrl-w                    # Enter Window mode
alt-ctrl-s                    # Enter Space mode
alt-ctrl-l                    # Enter Layout mode  
alt-ctrl-a                    # Enter App mode
alt-ctrl-m                    # Enter Maintenance mode

# Quick actions
alt-f                          # Fullscreen current window
cmd-enter                      # Launch Alacritty (quick terminal)
alt-shift-b                    # Launch Chrome Default profile

# System overrides (disabled macOS shortcuts)
cmd-h                          # Disabled (was "hide application")
```

### Window Mode (alt-ctrl-w) - Advanced Window Operations

```bash
# Exit
esc                            # Return to main mode

# Resize windows
s/d                            # Resize smart -50/+50
shift-s/d                      # Resize smart -100/+100

# Join containers (repurposed hjkl since focus moved to main)
h/j/k/l                        # Join with left/down/up/right window

# Monitor operations
m                              # Focus next monitor
shift-m                        # Move window to next monitor
ctrl-m                         # Move window to previous monitor

# Window operations
q                              # Close current window
shift-q                        # Close all windows except current
f                              # Toggle fullscreen

# Cross-mode switching
alt-ctrl-l                    # → Layout mode
alt-ctrl-a                    # → App mode
alt-ctrl-m                    # → Maintenance mode
```

### Space Mode (alt-ctrl-s) - Advanced Workspace Operations

```bash
# Exit
esc                            # Return to main mode

# Move window and follow (repurposed keys since switching moved to main)
1/2/3/a/b/c/e/t/m              # Move window to workspace and switch to it

# Workspace navigation
left/right                     # Previous/next workspace (wraps around)
up/down                        # Alternative prev/next navigation
tab                            # Toggle between recent workspaces

# Monitor operations
shift-left/right               # Move workspace to prev/next monitor

# Cross-mode switching
alt-ctrl-w                    # → Window mode
alt-ctrl-l                    # → Layout mode
alt-ctrl-a                    # → App mode
alt-ctrl-m                    # → Maintenance mode
```

### Layout Mode (alt-ctrl-l) - Layout Control

```bash
# Exit
esc                            # Return to main mode

# Layout types
t                              # Tiles layout (default tiling)
c                              # aCcordion layout (one large pane)
f                              # Toggle floating/tiling

# Orientation control
h                              # Force horizontal tiling
v                              # Force vertical tiling

# Container operations
r                              # Reset/flatten workspace layout
b                              # Balance all window sizes

# Quick layout switching
/                              # Quick tiles layout
,                              # Quick accordion layout  
.                              # Quick floating toggle

# Cross-mode switching
alt-ctrl-w                    # → Window mode
alt-ctrl-s                    # → Space mode
alt-ctrl-a                    # → App mode
alt-ctrl-m                    # → Maintenance mode
```

### App Mode (alt-ctrl-a) - Application Launching

```bash
# Exit
esc                            # Return to main mode

# Application launching (semantic keys match workspaces)
t                              # Launch Warp (Terminal → workspace T)
b                              # Launch Chrome Default (Browser → workspace B)
shift-b                        # Launch Chrome Profile 1 (Work browser)
s                              # Launch Safari
e                              # Launch Emacs (Editor → workspace E)
z                              # Launch Zed (Editor → workspace E)
c                              # Launch Calendar → workspace C
shift-c                        # Launch Google Chat → workspace M
a                              # Launch ChatGPT (AI → workspace A)
m                              # Launch Mail → workspace M
f                              # Launch Finder

# Cross-mode switching
alt-ctrl-w                    # → Window mode
alt-ctrl-s                    # → Space mode
alt-ctrl-l                    # → Layout mode
alt-ctrl-m                    # → Maintenance mode
```

### Maintenance Mode (alt-ctrl-m) - System Utilities

```bash
# Exit
esc                            # Return to main mode

# Configuration management
r                              # Reload AeroSpace configuration
shift-r                        # Restart AeroSpace completely

# Theme and visual management
t                              # Switch SketchyBar theme
shift-t                        # Advanced theme switch

# System utilities
s                              # Interactive screenshot to clipboard
shift-s                        # Screenshot to Desktop with timestamp

# Debug and diagnostics
d                              # Run debug script
l                              # Open Console app

# Backup and restore
b                              # Backup current config
shift-b                        # Open config directory

# Cross-mode switching
alt-ctrl-w                    # → Window mode
alt-ctrl-s                    # → Space mode
alt-ctrl-l                    # → Layout mode
```

## 🎨 Visual Configuration

### Window Gaps
```
┌──────────────────────────────────────────────────────────────┐
│                          ▲ 45px (Top gap)                   │
│  ┌────────────────────────────────────────────────────────┐  │
│  │  ◀ 10px (Left gap)      ┌───────────────┐      10px ▶  │  │
│  │                         │   Window 1    │              │  │
│  │                         ├───────────────┤              │  │
│  │   10px (Inner gap) ▶    │   Window 2    │   ◀ 10px     │  │
│  │                         └───────────────┘              │  │
│  └────────────────────────────────────────────────────────┘  │
│                          ▼ 5px (Bottom gap)                 │
└──────────────────────────────────────────────────────────────┘
```

- **Top gap**: 45px (menu bar clearance)
- **Left/Right gaps**: 10px each
- **Bottom gap**: 5px  
- **Inner gap**: 10px between windows

### Layout Settings
- **Default layout**: Tiles (automatic tiling)
- **Orientation**: Auto (wide monitors → horizontal, tall → vertical)
- **Accordion padding**: 30px visual indicator

## 🔗 Integrations

### SketchyBar Integration
- **Mode indicators**: Shows current mode in menu bar
- **Workspace indicators**: Displays current workspace
- **App icons**: Shows running apps in each workspace
- **Auto-refresh**: Updates on workspace/mode changes

### Borders Integration  
- **Active window**: Soft blue border `0xff8aadf4`
- **Inactive windows**: Dark gray border `0xff494d64`
- **Border width**: 1.5px (clean and subtle)
- **Style**: Square borders (snaps to window edge)

## 🤖 Auto-Assignment Rules

### Terminal Apps → Workspace T
- Warp (`dev.warp.Warp-Stable`)

### Browser Apps → Workspace B  
- Google Chrome (`com.google.Chrome`)
- Safari (`com.apple.Safari`)

### Editor Apps → Workspace E
- Zed (`dev.zed.Zed`)
- Emacs (`org.gnu.Emacs`) 
- Cursor (`com.todesktop.230313mzl4w4u92`)

### AI Tools → Workspace A
- ChatGPT (`com.openai.chat`)
- Google Gemini (Chrome app)

### Other Apps
- **Calendar** → Workspace C (`com.apple.iCal`)
- **Mail** → Workspace M
- **Google Chat** → Workspace M (`com.google.Chrome.app.mdpkiolbdkhdjpekfbkbmhigcaggjagi`)
- **LM Studio** → Workspace A (`ai.elementlabs.lmstudio`)

## 🚀 Startup Behavior

### Auto-Launch
- **AeroSpace**: Starts at login
- **SketchyBar**: Auto-launched by AeroSpace
- **Borders**: Auto-launched with custom colors

### Mouse Behavior
- **Focus follows mouse**: Cursor moves to center of focused monitor
- **Monitor switching**: Mouse follows when focus changes monitors

## 🛠️ Dependencies

### Required
- **AeroSpace**: Core window manager
- **SketchyBar**: Menu bar integration

### System Requirements
- **Accessibility permissions**: Required for window management
- **macOS shortcuts disabled**: `cmd-h` disabled to prevent conflicts

## ⚡ Quick Start Guide

### 1. Master the Frequent Operations (Main Mode)
```bash
# Window management (immediate access)
alt-h/j/k/l                    # Focus windows
alt-shift-h/j/k/l              # Move windows

# Workspace management (immediate access)  
alt-1/2/3                  # Switch to numbered workspaces
alt-a/b/c/e/t/m/z              # Switch to semantic workspaces
cmd-alt-[key]                  # Move window to workspace
```

### 2. Use Modes for Advanced Operations
```bash
# Advanced window operations
alt-ctrl-w                    # Resize, join, monitor ops

# Advanced workspace operations
alt-ctrl-s                    # Move-and-follow, navigation

# Layout control
alt-ctrl-l                    # Change layouts, containers

# App launching
alt-ctrl-a                    # Launch apps with semantic keys

# System maintenance  
alt-ctrl-m                    # Config, themes, utilities
```

### 3. Essential Workflows
```bash
# Daily window management
alt-h/j/k/l                    # Navigate between windows
alt-shift-h/j/k/l              # Rearrange windows
alt-1/2/3/a/b/e/t              # Switch workspaces

# Launch and organize
alt-ctrl-a, t                 # Launch Warp terminal
alt-ctrl-a, b                 # Launch Chrome browser  
alt-ctrl-a, z                 # Launch Zed editor
alt-ctrl-a, e                 # Launch Emacs editor

# Advanced operations when needed
alt-ctrl-w, s/d               # Resize windows
alt-ctrl-s, 1/2/3             # Move window and follow
alt-ctrl-l, t/c/f             # Change layouts
```

### 4. Power User Tips
- **80/20 optimization**: Most frequent operations require no mode switching
- **Cross-mode jumping**: Switch between modes without returning to main
- **Semantic keys**: App launcher keys match workspace letters
- **Auto-assignment**: Apps automatically move to designated workspaces
- **Single exit**: `esc` always returns to main from any mode

---

**Philosophy**: Hybrid approach optimizing for speed (frequent operations immediate) and organization (advanced operations in focused modes). Clean patterns, semantic organization, maximum efficiency.
