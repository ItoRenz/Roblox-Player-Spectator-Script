# 👁️ Roblox Player Spectator Script

A lightweight and feature-rich spectator mode script for Roblox games that allows players to spectate other players with a clean, intuitive interface.

## ✨ Features

- **Easy Toggle System**: Simple eye icon button to enable/disable spectator mode
- **Navigation Controls**: Arrow buttons to switch between players
- **Clean UI**: Minimalist design that doesn't obstruct gameplay
- **Mobile & PC Support**: Automatically detects device and adjusts UI accordingly
- **GUI Management**: 
  - Hides all player UI elements when spectating
  - Removes nametags, health bars, and billboard GUIs from spectated players
  - Preserves leaderboard visibility
  - Restores all UI when spectating ends
- **Auto-Updates**: Automatically handles player joins/leaves during spectation
- **Smooth Transitions**: Seamless camera switching between players

## 🎮 How to Use

1. **Installation**:
   - Open Roblox Studio
   - In Explorer, navigate to `StarterGui`
   - Create a new `LocalScript`
   - Copy and paste the script code
   - Save and test in-game

2. **Controls**:
   - Click the **eye icon (👁️)** to toggle spectator mode
   - Use **◀** button to spectate previous player
   - Use **▶** button to spectate next player
   - Player name display shows current spectated player

3. **Visual Indicators**:
   - **Gray button**: Spectator mode OFF
   - **Red button**: Spectator mode ON
   - Info label displays: `DisplayName (@Username)`

## 📱 Device Compatibility

### Mobile
- Toggle button: 25x25px
- Positioned on right side at middle height
- Touch-optimized button sizes
- Compact info label (240x20px)

### PC
- Toggle button: 30x30px
- Positioned on right side
- Larger navigation arrows
- Standard info label (280x30px)

## 🎨 UI Specifications

| Element | Mobile | PC |
|---------|--------|-----|
| Toggle Button Size | 25x25px | 30x30px |
| Toggle Position | Right-center | Right-center |
| Toggle Text Size | 20 | 25 |
| Info Label Size | 240x20px | 280x30px |
| Info Label Text Size | 14 | 16 |
| Info Background Opacity | 50% | 50% |

## 🔧 Technical Details

- **Services Used**: Players, UserInputService, RunService, StarterGui
- **Device Detection**: Automatic via TouchEnabled and MouseEnabled
- **GUI Hiding System**: 
  - Hides BillboardGui, SurfaceGui
  - Disables Humanoid display distance
  - Hides TextLabel, TextButton, TextBox in Head
  - Monitors new descendants dynamically
- **State Management**: Preserves original UI states for restoration
- **Error Handling**: Protected calls (pcall) for stability

## 🚀 Features in Detail

### Smart GUI Management
The script intelligently hides UI elements from spectated players:
- Removes overhead nametags and health bars
- Hides all billboard and surface GUIs
- Conceals custom text elements
- Dynamically handles newly added UI elements

### CoreGui Handling
- Hides: Health, Backpack, Chat, Emotes Menu
- Preserves: Leaderboard/PlayerList
- Restores original states when exiting spectator mode

### Player Management
- Automatically updates player list
- Handles player disconnections gracefully
- Supports respawning players
- Maintains spectator state consistency

## 📝 Notes

- The script only spectates players with active characters (Humanoid present)
- All UI changes are temporary and restored when spectating ends
- The script respects original UI states and doesn't permanently modify them
- Compatible with most Roblox games without conflicts

## 🐛 Known Limitations

- Cannot spectate players without characters
- Requires LocalScript in StarterGui to function
- Some custom UI systems may not be fully hidden

## 📄 License

This script is provided as-is for use in Roblox games. Feel free to modify and distribute.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 💡 Tips

- For best experience, ensure the script runs on client-side (LocalScript)
- Test in different game environments for compatibility
- Customize button positions and sizes as needed for your game

---

**Version**: 1.0  
**Last Updated**: October 2025  
**Compatibility**: Roblox Studio (Current Version)
