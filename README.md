# AeroSpace Configuration

Refactored AeroSpace tiling window manager with optimized hybrid approach: frequent operations in main mode, advanced operations in focused modes.

## 🚀 Hybrid Mode System

### Core Philosophy
- **Frequent operations (80%)**: Direct access in main mode with clean prefixes
- **Advanced operations (20%)**: Organized in specialized modes
- **Best of both worlds**: Speed for daily workflows + organization for complex operations

### Mode Overview
- **Main Mode**: Window focus/movement, workspace switching, move-to-workspace
- **cmd-shift-w** = **Window** mode (resize, join, monitor, close operations)
- **cmd-shift-s** = **Space** mode (move-and-follow, navigation, monitor ops)
- **cmd-shift-l** = **Layout** mode (layouts, containers)
- **cmd-shift-a** = **App** mode (application launching)
- **cmd-shift-m** = **Maintenance** mode (system utilities, config, themes)

### Mode Navigation
- **Single exit**: `esc` always returns to main mode
- **Cross-mode switching**: Jump between modes without returning to main
- **No self-switching**: Can't switch to the mode you're already in

## 🎯 Workspace Organization

### 12 Configured Workspaces
- **1-5**: Project workspaces (organize windows by project)
- **A**: AI tools (ChatGPT, Google Gemini)
- **B**: Browsers (Chrome, Safari) 
- **C**: Calendar
- **E**: Editors (Zed, Emacs, Cursor)
- **T**: Terminals (Alacritty, Warp)
- **M**: Messages (Google Chat)
- **Z**: Meetings (Zoom)

## ⌨️ Keybinding Reference

### Main Mode (Always Active) - Frequent Operations

#### Window Operations (Immediate Access)
```bash
# Window focus (vim-style) - MOST FREQUENT
alt-h/j/k/l                    # Focus left/down/up/right

# Window movement - VERY FREQUENT  
alt-shift-h/j/k/l              # Move window left/down/up/right
```

#### Workspace Operations (Immediate Access)
```bash
# Workspace switching - VERY FREQUENT
alt-tab                        # Back-and-forth between recent workspaces
alt-1/2/3/4/5                  # Switch to numbered workspaces  
alt-a/b/c/e/t/m/z              # Switch to semantic workspaces

# Move window to workspace - FREQUENT
cmd-alt-1/2/3/4/5              # Move window to numbered workspace
cmd-alt-a/b/c/e/t/m/z          # Move window to semantic workspace
```

#### Essential Shortcuts
```bash
# Mode switching
cmd-shift-w                    # Enter Window mode
cmd-shift-s                    # Enter Space mode
cmd-shift-l                    # Enter Layout mode  
cmd-shift-a                    # Enter App mode
cmd-shift-m                    # Enter Maintenance mode

# Quick actions
alt-f                          # Fullscreen current window

# System overrides (disabled macOS shortcuts)
cmd-h                          # Disabled (was "hide application")
```

### Window Mode (cmd-shift-w) - Advanced Window Operations

```bash
# Exit
esc                            # Return to main mode

# Resize windows
-/=                            # Resize smart -50/+50
shift--/=                      # Resize smart -100/+100

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
cmd-shift-l                    # → Layout mode
cmd-shift-a                    # → App mode
cmd-shift-m                    # → Maintenance mode
```

### Space Mode (cmd-shift-s) - Advanced Workspace Operations

```bash
# Exit
esc                            # Return to main mode

# Move window and follow (repurposed keys since switching moved to main)
1-5, a,b,c,e,t,m,z            # Move window to workspace and switch to it

# Workspace navigation
left/right                     # Previous/next workspace (wraps around)
up/down                        # Alternative prev/next navigation
tab                            # Toggle between recent workspaces

# Monitor operations
shift-left/right               # Move workspace to prev/next monitor

# Cross-mode switching
cmd-shift-w                    # → Window mode
cmd-shift-l                    # → Layout mode
cmd-shift-a                    # → App mode
cmd-shift-m                    # → Maintenance mode
```

### Layout Mode (cmd-shift-l) - Layout Control

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
cmd-shift-w                    # → Window mode
cmd-shift-s                    # → Space mode
cmd-shift-a                    # → App mode
cmd-shift-m                    # → Maintenance mode
```

### App Mode (cmd-shift-a) - Application Launching

```bash
# Exit
esc                            # Return to main mode

# Application launching (semantic keys match workspaces)
t                              # Launch Alacritty (Terminal → workspace T)
b                              # Launch Chrome Default (Browser → workspace B)
shift-b                        # Launch Chrome Profile 1 (Work browser)
s                              # Launch Safari
e                              # Launch Zed (Editor → workspace E)
shift-e                        # Launch Emacs (Alternative editor)
c                              # Launch Calendar → workspace C
a                              # Launch ChatGPT (AI → workspace A)
m                              # Launch Messages → workspace M
f                              # Launch Finder
n                              # Launch Notes

# Cross-mode switching
cmd-shift-w                    # → Window mode
cmd-shift-s                    # → Space mode
cmd-shift-l                    # → Layout mode
cmd-shift-m                    # → Maintenance mode
```

### Maintenance Mode (cmd-shift-m) - System Utilities

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
cmd-shift-w                    # → Window mode
cmd-shift-s                    # → Space mode
cmd-shift-l                    # → Layout mode
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
- Alacritty (`org.alacritty`)
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
- **Calendar** → Workspace C
- **Google Chat** → Workspace M  
- **Zoom** → Workspace Z

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
- **Borders**: Window border highlighting

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
alt-1/2/3/4/5                  # Switch to numbered workspaces
alt-a/b/c/e/t/m/z              # Switch to semantic workspaces
cmd-alt-[key]                  # Move window to workspace
```

### 2. Use Modes for Advanced Operations
```bash
# Advanced window operations
cmd-shift-w                    # Resize, join, monitor ops

# Advanced workspace operations
cmd-shift-s                    # Move-and-follow, navigation

# Layout control
cmd-shift-l                    # Change layouts, containers

# App launching
cmd-shift-a                    # Launch apps with semantic keys

# System maintenance  
cmd-shift-m                    # Config, themes, utilities
```

### 3. Essential Workflows
```bash
# Daily window management
alt-h/j/k/l                    # Navigate between windows
alt-shift-h/j/k/l              # Rearrange windows
alt-1/2/3/a/b/e/t              # Switch workspaces

# Launch and organize
cmd-shift-a, t                 # Launch terminal
cmd-shift-a, b                 # Launch browser  
cmd-shift-a, e                 # Launch editor

# Advanced operations when needed
cmd-shift-w, -/=               # Resize windows
cmd-shift-s, 1-5               # Move window and follow
cmd-shift-l, t/c/f             # Change layouts
```

### 4. Power User Tips
- **80/20 optimization**: Most frequent operations require no mode switching
- **Cross-mode jumping**: Switch between modes without returning to main
- **Semantic keys**: App launcher keys match workspace letters
- **Auto-assignment**: Apps automatically move to designated workspaces
- **Single exit**: `esc` always returns to main from any mode

---

**Philosophy**: Hybrid approach optimizing for speed (frequent operations immediate) and organization (advanced operations in focused modes). Clean patterns, semantic organization, maximum efficiency.