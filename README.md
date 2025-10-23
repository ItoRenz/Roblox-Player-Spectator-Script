# 👁️ Roblox Player Spectator Script

<div align="center">

![Version](https://img.shields.io/badge/version-2.1-blue.svg)
![Platform](https://img.shields.io/badge/platform-Roblox-red.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Author](https://img.shields.io/badge/author-ItoRenz00-orange.svg)

A comprehensive spectator system for Roblox games that provides a clean, distraction-free viewing experience with automatic GUI hiding for all players.

**Created by [ItoRenz00](https://github.com/ItoRenz00)**

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Configuration](#-configuration) • [Changelog](#-changelog)

</div>

---

## ✨ Features

### 🎮 Core Functionality
- **👁️ One-Click Toggle**: Simple eye icon button to enter/exit spectator mode
- **⬅️➡️ Player Navigation**: Seamlessly switch between players using arrow buttons
- **📱 Cross-Platform**: Optimized UI layouts for both mobile and desktop devices
- **🔄 Smart State Management**: Proper restoration of all GUI elements on exit

### 🎯 Advanced GUI Hiding
The script automatically hides **ALL** player GUIs during spectate mode:
- ✅ Player nametags and health bars
- ✅ BillboardGuis above all player heads
- ✅ SurfaceGuis and custom text elements
- ✅ Core game UI (health, backpack, chat, emotes menu)
- ✅ Custom ScreenGuis (except spectator controls)

### 🛡️ Robust Player Management
- **Auto-Update**: Handles players joining/leaving automatically
- **Dynamic Tracking**: Monitors newly added GUI elements
- **Safe Cleanup**: Proper data cleanup on player removal
- **Respawn Handling**: Restores GUIs correctly on character respawn

---

## 📋 Requirements

- Roblox Studio or a published Roblox game
- LocalScript execution capability
- No additional plugins or modules required

---

## 🚀 Installation

### Method 1: Roblox Studio

1. Open your game in **Roblox Studio**
2. Navigate to **StarterGui** in the Explorer panel
3. Right-click → **Insert Object** → **LocalScript**
4. Copy and paste the entire script code
5. Rename to `SpectatorScript` (optional)
6. **Test in Play mode** (F5 or F7)

### Method 2: Direct Import

```lua
-- Simply copy the script file into StarterGui
-- No additional setup required
```

### Verification

After installation, you should see this in the Output console:
```
═══════════════════════════════════════════════════════════════
✓ Spectator Script Loaded Successfully!
✓ Version: 2.1
✓ Device: PC (or Mobile)
✓ Feature: Hides ALL players' GUIs during spectate
═══════════════════════════════════════════════════════════════
```

---

## 🎮 Usage

### Controls

#### 🖥️ PC Controls
| Action | Control |
|--------|---------|
| Toggle Spectator Mode | Click **👁️ Eye Icon** (right side of screen) |
| Previous Player | Click **◀ Previous Button** (left side) |
| Next Player | Click **▶ Next Button** (right side) |
| Exit Spectator | Click **👁️ Eye Icon** again |

#### 📱 Mobile Controls
| Action | Control |
|--------|---------|
| Toggle Spectator Mode | Tap **👁️ Eye Icon** (right side of screen) |
| Previous Player | Tap **◀ Previous Button** (left side) |
| Next Player | Tap **▶ Next Button** (right side) |
| Exit Spectator | Tap **👁️ Eye Icon** again |

### Visual Indicators

| Indicator | Meaning |
|-----------|---------|
| 🔘 **Gray Eye Icon** | Spectator mode is **OFF** |
| 🔴 **Red Eye Icon** | Spectator mode is **ON** |
| 📝 **Info Label** | Shows current spectated player's name |

### User Experience

When you activate spectator mode:
1. All player GUIs instantly disappear (yours and others)
2. Camera smoothly transitions to target player
3. Navigation controls appear for easy player switching
4. Your character remains in the game world
5. Other players cannot see that you're spectating

When you exit spectator mode:
1. All GUIs restore to their original state
2. Camera returns to your character
3. Game UI elements reappear
4. Normal gameplay resumes

---

## 🔧 Configuration

### Button Positioning

Customize button locations by editing these values:

```lua
-- Toggle Button Position (PC)
toggleButton.Position = UDim2.new(1, -35, 0.5, -200)

-- Toggle Button Position (Mobile)
toggleButton.Position = UDim2.new(1, -35, 0.5, -110)

-- Previous Button Position (PC)
prevButton.Position = UDim2.new(0, 15, 0.5, -40)

-- Next Button Position (PC)
nextButton.Position = UDim2.new(1, -75, 0.5, -40)
```

### Button Sizing

Adjust button sizes for different screen sizes:

```lua
-- PC Button Size
toggleButton.Size = UDim2.new(0, 30, 0, 30)

-- Mobile Button Size
toggleButton.Size = UDim2.new(0, 25, 0, 25)
```

### Color Customization

Change the color scheme to match your game:

```lua
-- Default State (Inactive)
BackgroundColor3 = Color3.fromRGB(45, 45, 45)

-- Active State (Spectating)
BackgroundColor3 = Color3.fromRGB(200, 50, 50)

-- Info Label Background
BackgroundColor3 = Color3.fromRGB(0, 0, 0)
```

### Text Sizing

Modify text sizes for better readability:

```lua
-- PC Text Size
toggleButton.TextSize = 25

-- Mobile Text Size
toggleButton.TextSize = 20
```

---

## 🐛 Known Issues & Limitations

| Issue | Status | Workaround |
|-------|--------|------------|
| Brief flicker on player respawn | Known | Minimal impact on UX |
| Dynamic GUIs added mid-spectate may appear briefly | Known | Handled by DescendantAdded listener |
| Camera may jitter if spectated player moves erratically | Engine Limitation | None available |

---

## 🔄 Changelog

### Version 2.1 (Current) - Major Update
- ✅ **FIXED**: All players' GUIs now hidden during spectate mode
- ✅ **FIXED**: Local player's GUI no longer visible to spectators
- ✅ **FIXED**: GUI restoration works perfectly when switching targets
- ✅ **NEW**: Added `hideAllPlayersGui()` function
- ✅ **NEW**: Added `showAllPlayersGui()` function
- ✅ **IMPROVED**: Simplified player switching logic
- ✅ **IMPROVED**: Enhanced code documentation and structure
- ✅ **IMPROVED**: Better state management with clearer variable names

### Version 2.0 - Bug Fix Release
- ✅ Fixed BillboardGui restoration bug
- ✅ Improved state management with per-player tracking
- ✅ Added proper cleanup on player removal
- ✅ Enhanced error handling throughout
- ✅ Optimized GUI hiding/showing logic

### Version 1.0 - Initial Release
- ✨ Basic spectator functionality
- ✨ Mobile and PC support
- ✨ Player navigation
- ✨ GUI hiding for spectated player

---

## 📚 Technical Details

### Architecture

```
┌─────────────────────────────────────┐
│      Spectator Script System        │
├─────────────────────────────────────┤
│                                     │
│  ┌───────────────────────────┐     │
│  │   GUI Management Layer    │     │
│  │  • Hide/Show Functions    │     │
│  │  • State Tracking         │     │
│  └───────────────────────────┘     │
│             │                       │
│  ┌───────────────────────────┐     │
│  │  Spectator Core Logic     │     │
│  │  • Player List Management │     │
│  │  • Camera Control         │     │
│  │  • Navigation System      │     │
│  └───────────────────────────┘     │
│             │                       │
│  ┌───────────────────────────┐     │
│  │   Event Handlers          │     │
│  │  • Player Join/Leave      │     │
│  │  • Character Respawn      │     │
│  │  • Button Clicks          │     │
│  └───────────────────────────┘     │
│                                     │
└─────────────────────────────────────┘
```

### State Management

The script uses a per-player state tracking system:

```lua
hiddenObjectsPerPlayer = {
    [userId1] = {
        [guiObject1] = originalState,
        [guiObject2] = originalState,
        ["humanoidDisplay"] = originalDisplayType
    },
    [userId2] = { ... }
}
```

This ensures that each player's GUI state is independently tracked and restored correctly.

### Performance Considerations

- **Memory Efficient**: Only stores necessary state data
- **Optimized Loops**: Uses pcall for error handling without crashes
- **Event-Driven**: Minimal overhead with smart event listeners
- **Cleanup**: Automatic data cleanup on player removal

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Reporting Bugs

1. Check existing issues first
2. Provide detailed reproduction steps
3. Include your Roblox Studio version
4. Share relevant error messages from Output

### Suggesting Features

- Open an issue with the `enhancement` label
- Describe the feature and its use case
- Explain how it benefits the community

### Pull Requests

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Style Guidelines

- Use clear, descriptive variable names
- Add comments for complex logic
- Follow the existing code structure
- Test thoroughly before submitting

---

## 📝 License

This project is licensed under the **MIT License** - you are free to:

- ✅ Use commercially
- ✅ Modify the code
- ✅ Distribute copies
- ✅ Use privately

**Conditions:**
- Include the original license and copyright notice
- No warranty is provided

See the [LICENSE](LICENSE) file for full details.

---

## ⚠️ Important Notes

### Script Placement
- ⚠️ **Must** be placed in **StarterGui**
- ⚠️ **Must** be a **LocalScript**, not a regular Script
- ⚠️ Will only work in games where LocalScripts can execute

### Compatibility
- ✅ Works with Filtering Enabled (FE)
- ✅ Compatible with most Roblox games
- ✅ Tested on mobile and desktop platforms
- ⚠️ Some game-specific UI may require manual configuration

### Security
- 🔒 Client-side only (no server communication)
- 🔒 Cannot affect other players' gameplay
- 🔒 No remote event exploits possible
- 🔒 Safe to use in any game

---

## 💡 Tips & Best Practices

### For Players
- 🎯 Use spectator mode to learn from skilled players
- 🎥 Great for recording cinematic footage
- 🏆 Perfect for observing tournaments or competitions
- 📸 Take screenshots from unique angles

### For Developers
- 🔧 Test your game from different perspectives
- 🐛 Debug player-specific issues easily
- 🎨 Review your map design from player viewpoints
- 🎬 Create promotional videos and trailers

### Optimization Tips
- Keep GUI elements lightweight for better performance
- Limit the number of BillboardGuis per character
- Use TextScaled cautiously to avoid lag
- Consider disabling spectator in competitive modes if needed

---

## 🔍 Troubleshooting

### Script Not Working

**Problem**: Nothing happens when clicking the eye icon

**Solutions**:
1. Check if script is in **StarterGui**
2. Verify it's a **LocalScript**
3. Check Output for error messages
4. Ensure game allows LocalScript execution

### GUIs Not Hiding

**Problem**: Player GUIs still visible during spectate

**Solutions**:
1. Check if GUIs are using custom parent structures
2. Verify BillboardGui.Adornee is set correctly
3. Some admin GUIs may override visibility
4. Check for conflicting scripts

### Camera Not Following Player

**Problem**: Camera doesn't move to spectated player

**Solutions**:
1. Ensure target player has a Humanoid
2. Check if another script is controlling camera
3. Verify CameraType is not locked to Fixed
4. Try rejoining the game

### Button Position Wrong

**Problem**: Buttons appear off-screen or in wrong location

**Solutions**:
1. Adjust Position values in configuration
2. Check device detection (isMobile variable)
3. Test on different screen sizes
4. Modify UDim2 values as needed

---

## 📧 Support

### Getting Help

- 📖 Read this documentation thoroughly
- 🔍 Search existing GitHub issues
- 💬 Ask in the Discussions section
- 🐛 Report bugs via Issues tab

### Contact

- **GitHub Issues**: For bug reports and feature requests
- **Discussions**: For general questions and community help
- **Pull Requests**: For code contributions

---

## 🌟 Acknowledgments

- Created by **ItoRenz00**
- Thanks to the Roblox developer community for feedback and testing
- Inspired by various spectator systems in popular games
- Built with performance and user experience in mind

---

## 📊 Project Stats

- **Lines of Code**: ~600
- **Functions**: 15+
- **Event Handlers**: 6
- **Supported Platforms**: PC, Mobile, Tablet
- **Roblox Engine**: Compatible with latest version

---

## 🎯 Roadmap

### Planned Features (Future Updates)

- [ ] **v2.2**: Add keyboard shortcuts for PC users
- [ ] **v2.3**: Implement player search/filter system
- [ ] **v2.4**: Add spectator list UI with thumbnails
- [ ] **v2.5**: Custom camera angles and zoom levels
- [ ] **v3.0**: Replay system with recording capability

### Community Requests

Vote for features on our GitHub Issues page!

---

## 📜 Version History

| Version | Release Date | Key Changes |
|---------|--------------|-------------|
| 2.1 | 2024 | Hide all players' GUIs, improved state management |
| 2.0 | 2024 | Fixed GUI restoration bugs, per-player tracking |
| 1.0 | 2024 | Initial release with basic spectator features |

---

<div align="center">

### 🎮 Happy Spectating! 👁️

Made with ❤️ by **[ItoRenz00](https://github.com/ItoRenz00)** for the Roblox Developer Community

[⬆ Back to Top](#-roblox-player-spectator-script)

---

**Star ⭐ this repository if you found it helpful!**

</div>
