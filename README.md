# Walli 🌊

**Walli** is a modern, native macOS application that brings your desktop to life with video wallpapers. It supports playlists, multi-monitor setups, and seamless lock screen integration via a companion screen saver.

## ✨ Features

- **Live Video Wallpapers**: Play `.mp4`, `.mov`, and other video formats as your desktop background.
- **Lock Screen Support**: 
  - Automatically syncs a static frame to the system lock screen.
  - Includes a companion **Screen Saver** extension for full video playback while locked.
- **Smart Performance**:
  - **Pause on Focus Change**: Automatically pauses playback when you are working in other apps to save resources.
  - **Pause on Inactivity**: Pauses playback when the system is idle.
- **Playlists**: Create collections of wallpapers that cycle automatically.
- **Multi-Monitor**: Supports multiple displays with different or synchronized wallpapers.
- **Native macOS UI**: Built with SwiftUI for a clean, modern aesthetic.

## 🚀 Installation

### 1. Build from Source
Walli uses `xcodegen` to manage the Xcode project.

**Prerequisites:**
- macOS 13.0 or later
- Xcode 15+
- [XcodeGen](https://github.com/yonaskolb/XcodeGen) (`brew install xcodegen`)

**Build:**
Run the included build script to generate the project and create a DMG:

```bash
./build.sh
```

This will create `build/Walli.dmg` containing the App and the Screen Saver.

### 2. Install the App
1. Open `build/Walli.dmg`.
2. Drag **Walli.app** to your `Applications` folder.
3. Launch Walli.

### 3. Enable Lock Screen Video
Due to macOS security restrictions, standard apps cannot play video on the Lock Screen. Walli solves this with a companion Screen Saver.

1. In the DMG (or build folder), double-click **WalliSaver.saver**.
2. When prompted, install it (either for "This User" or "All Users").
3. Open **System Settings** -> **Screen Saver**.
4. Scroll down to "Other" and select **WalliSaver**.
5. (Optional) In **Lock Screen** settings, you can set "Start Screen Saver when inactive" to "Immediately" if you want the video to appear as soon as you lock your Mac.

## 🛠 Usage

1. **Add Wallpapers**: Drag and drop video files into the library window, or click the "+" button.
2. **Set Wallpaper**: Right-click a video and select "Set as Desktop Wallpaper".
3. **Playlists**: Create a playlist in the sidebar, add videos, and click "Play" to cycle through them.
4. **Settings**:
   - Toggle "Launch at Login".
   - Enable/Disable "Pause on Focus Change" to save battery.
   - Configure "Pause on Inactivity" timers.

## 🏗 Development

The project structure is defined in `project.yml`. If you make changes to the project structure, run:

```bash
xcodegen generate
```

- **Walli**: Main macOS Application target (SwiftUI).
- **WalliSaver**: Screen Saver Bundle target (AppKit/ScreenSaver).
- **Core**: Shared logic for wallpaper engine and persistence.

## 📄 License

This project is open source.
