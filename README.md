# Discord ARM
My approach to port Discord Client for the Linux AArch64 (ARM64).

## How to reproduce this:
- Download `tar.gz` containing the Discord binaries for Linux X86-64.
- Download the Electron binaries for Linux AArch64 (or ARMv7).
- Extract the archives to the different folders:
```
├── discord
│   ├── (...)
│   └── discord-binary
└── electron
    ├── (...)
    └── electron-binary
```
- Remove `resources/` from the Electron folder.
- Move `resources/` folder from the Discord folder to the Electron ones.
- See it *running* once executing `electron` binary from the Electron folder.

## Current state:
### What works:
- Discord updater;
- UI (GTK);
- Tray icon/menu;

### What doesn't work:
- Web content (it doesn't load because of the pre-compiled X86_64 `*.node` addon modules);
- ...and because of the above, almost everything else can't be confirmed if it works or not;

### Currently failing on:
```
$HOME/.config/discord/0.0.13/modules/discord_utils/discord_utils.node
```
(*ELF 64-bit LSB shared object, x86-64*)

## Tips for debugging:
- To get the DevTools visible, press \[SHIFT+ALT+I\] on your keyboard.
