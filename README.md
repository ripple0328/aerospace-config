# Aerospace Configuration

Current Aerospace tiling window manager setup with custom workspace organization and integrations.

## 🎯 Workspace Organization

### 9 Configured Workspaces
- **1, 2, 3**: Project workspaces (organize windows by project)
- **A**: AI tools (ChatGPT, Google Gemini)
- **B**: Browsers (Chrome, Safari)
- **C**: Calendar
- **E**: Editors (Zed, Emacs, Cursor)
- **T**: Terminals (Alacritty, Warp)
- **M**: Messages (Google Chat)
- **Z**: Meetings (Zoom)

### Workspace Switching
```bash
Alt + [1,2,3,A,B,C,E,T,M,Z]    # Switch to workspace
Alt + Shift + [same keys]       # Move window to workspace
Alt + Tab                       # Back-and-forth between recent workspaces
Alt + Shift + Tab              # Move workspace to next monitor
```

## ⌨️ Configured Shortcuts

### Window Navigation
```bash
Alt + H/J/K/L                  # Focus left/down/up/right
Alt + Shift + H/J/K/L          # Move window left/down/up/right
```

### Layouts
```bash
Alt + /                        # Toggle horizontal/vertical tiling
Alt + ,                        # Toggle accordion layout
Alt + F                        # Fullscreen current window
```

### Window Management
```bash
Alt + Shift + -                # Shrink window (smart resize)
Alt + Shift + =                # Expand window (smart resize)
Alt + Q                        # Close all windows except current
```

### Application Launchers
```bash
Cmd + Shift + T                # Launch Alacritty terminal
Cmd + Shift + B                # Launch Chrome (Default profile)
Cmd + Shift + W                # Launch Chrome (Profile 1)
Cmd + Shift + S                # Launch Safari
Cmd + Shift + A                # Launch ChatGPT
Cmd + Shift + E                # Launch Emacs
Cmd + Shift + C                # Launch Calendar
Cmd + Shift + Z                # Launch Zed editor
```

### Service Mode (`Alt + Shift + ;`)
```bash
Esc                            # Reload config and exit service mode
R                              # Reset/flatten workspace layout
F                              # Toggle floating/tiling for current window
Backspace                      # Close all windows except current
Alt + Shift + H/J/K/L          # Join current window with direction
```

### System
```bash
Ctrl + Shift + S               # Screenshot selection to clipboard
```

## 🎨 Visual Configuration

### Window Gaps
<pre>
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
</pre>

- **Top gap**: 45px (for menu bar clearance)
- **Left/Right gaps**: 10px each
- **Bottom gap**: 5px
- **Inner gap**: 10px between windows

### Layout Settings
- **Default layout**: Tiles (automatic window arrangement)
- **Orientation**: Auto (wide monitors → horizontal, tall → vertical)
- **Accordion padding**: 30px visual indicator

## 🔗 Integrations

### SketchyBar Integration
- **Workspace indicators**: Shows current workspace in menu bar
- **App icons**: Displays running apps in each workspace
- **Mode indicator**: Shows service mode status
- **Auto-refresh**: Updates on workspace changes

### Borders Integration
- **Style**: Square borders (no gap, snaps to window edge)
- **Active window**: Soft blue border ` 0xff8aadf4`
- **Inactive windows**: Dark gray border ` 0xff494d64`
- **Border width**: 1.5px (subtle and clean)

## 🤖 Auto-Assignment Rules

### Terminal Apps → Workspace T
- Alacritty (`org.alacritty`)
- Warp (`dev.warp.Warp-Stable`)

### Browsers → Workspace B
- Google Chrome (`com.google.Chrome`)
- Safari (`com.apple.Safari`)

### Editors → Workspace E
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
- **Aerospace**: Starts at login
- **SketchyBar**: Auto-launched by Aerospace
- **Borders**: Auto-launched with custom colors

### Mouse Behavior
- **Focus follows mouse**: Cursor moves to center of focused monitor
- **Monitor switching**: Mouse follows when focus changes monitors

## 🛠️ Dependencies

### Required
- **Aerospace**: Core window manager
- **SketchyBar**: Menu bar integration
- **Borders**: Window border highlighting

### System
- **Accessibility permissions**: Required for window management
- **Disabled features**: `Cmd + H` (hide application) disabled

## ⚡ Quick Start

1. **Project workspaces**: `Alt + 1/2/3` for different projects
2. **Tool workspaces**: `Alt + A` (AI), `Alt + B` (Browser), `Alt + E` (Editor), `Alt + T` (Terminal)
3. **Launch apps**: `Cmd + Shift + T` (Terminal), `Cmd + Shift + B` (Chrome)
4. **Navigate windows**: `Alt + H/J/K/L`
5. **Service mode**: `Alt + Shift + ;` for advanced operations

---

**Note**: All apps automatically move to their designated workspaces when opened. Focus with navigation keys, not mouse clicks for best experience.
