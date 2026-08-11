# PinAnyApp

PinAnyApp is a native macOS menu-bar utility that mirrors any open window into a floating, always-on-top preview. It uses Apple's system window picker and ScreenCaptureKit, so the person using the Mac always controls which window is shared.

## Requirements

- macOS 14 Sonoma or newer
- Xcode 16.2 or newer (the Swift command-line tools are enough to build)

## Run it

```sh
make run
```

The built app is placed at `.build/PinAnyApp.app`. Click the pin in the menu bar, choose **Choose a window**, and select a window in the system picker.

You can pin up to 12 windows, hide or unpin them independently, include or exclude the cursor, show the previews on every Space, and optionally link an original application window.

## Linked original windows

macOS does not provide a public API for embedding another application inside a PinAnyApp window. On macOS 15.2 or newer, click the link button beside a pin to use the closest public alternative. PinAnyApp hides the video mirror and repeatedly raises the selected original window using Accessibility. Because it is the application's real window, clicks, keyboard input, menus, drag and drop, and accessibility all work normally.

Click the blue link again to stop raising the original and restore the floating video preview. Linked originals remain on their current Space and can't float above system-owned panels or full-screen isolation boundaries.

## Develop in Xcode

Open `Package.swift` in Xcode and run the `PinAnyApp` scheme, or use:

```sh
swift build
swift test
```

PinAnyApp only uses public macOS APIs. The preview is view-only; linked-original mode provides native interaction without synthetic input.
