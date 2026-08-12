<div align="center">

# PinAnyApp

### Keep any macOS window visible while you work.

[![Swift 5.10](https://img.shields.io/badge/Swift-5.10-F05138?logo=swift&logoColor=white)](https://www.swift.org)
[![macOS 14+](https://img.shields.io/badge/macOS-14%2B-000000?logo=apple&logoColor=white)](https://www.apple.com/macos/)
![Status: Alpha](https://img.shields.io/badge/status-alpha-5B8C78)

PinAnyApp is a native menu-bar utility that turns any open window into a floating, always-on-top preview. Pick a window with the macOS system picker, place it where you need it, and keep the important parts of your workspace in sight.

</div>

> [!NOTE]
> PinAnyApp is currently in alpha development. Downloads and source code will be published when the first public build is ready.

## Preview

<!-- Add the UI walkthrough here when it is ready:
<p align="center">
  <img src="Support/PinAnyApp-Demo.gif" alt="PinAnyApp UI walkthrough" width="760">
</p>
-->

_UI walkthrough coming soon._

## Features

- Pin up to 12 windows at once
- Keep previews floating above other windows
- Show previews on the current Space or every Space
- Hide, restore, and close each preview independently
- Include or exclude the pointer from captured content
- Choose Low, Standard, or High resolution per preview
- Select windows through Apple's privacy-preserving system picker

## How it works

PinAnyApp uses ScreenCaptureKit to mirror the window you select into a lightweight floating panel. macOS remains in control of window selection and screen-recording permission.

Previews are intentionally view-only. Mouse clicks, keyboard input, and other interactions continue to belong to the original application.

## Requirements

- macOS 14 Sonoma or newer
- Xcode 16.2 or newer to build from source

## Development

Once the source is published, open `Package.swift` in Xcode and run the `PinAnyApp` scheme, or use the command line:

```sh
swift build
swift test
make run
```

The packaged app is written to `.build/PinAnyApp.app`.

## Privacy

PinAnyApp uses public macOS APIs and does not synthesize input. Window capture is subject to macOS Screen Recording permission, and the system window picker always makes the selected content explicit.
