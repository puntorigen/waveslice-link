# WaveSlice Link

A small program that lets [WaveSlice](https://waveslice3d.com) talk to the 3D printers on your network. A web page cannot reach a printer's LAN API by itself, so the Link listens on `127.0.0.1:9283` for WaveSlice and passes its requests on: printer discovery, the printer's HTTP API and the camera stream. It keeps nothing, writes nothing to disk, never goes online, and only answers pages from WaveSlice's own origins.

This repository holds the **downloads**; the source lives with WaveSlice.

## Install

Download the file for your computer from the [latest release](https://github.com/puntorigen/waveslice-link/releases/latest), run it and leave it open while you use WaveSlice. In WaveSlice, open the printer menu and choose *Connect*: it finds the Link by itself.

| Computer | File |
| --- | --- |
| Mac with Apple silicon | `waveslice-link-darwin-arm64` |
| Mac with Intel | `waveslice-link-darwin-x64` |
| Windows | `waveslice-link-windows-x64.exe` |
| Windows on ARM | `waveslice-link-windows-arm64.exe` |
| Linux | `waveslice-link-linux-x64` / `waveslice-link-linux-arm64` |

The files are not code-signed yet. On a Mac, right-click the file and choose *Open* the first time, or from Terminal:

```
chmod +x waveslice-link-darwin-arm64
xattr -d com.apple.quarantine waveslice-link-darwin-arm64
./waveslice-link-darwin-arm64
```

On Windows, SmartScreen asks for *More info → Run anyway*. `SHA256SUMS.txt` in each release has the checksums.

```
waveslice-link [--port 9283] [--version] [--help]
```

## Printers

FlashForge machines with the LAN API (Creator 5, Creator 5 Pro, Adventurer 5M, Adventurer 5M Pro), with *LAN Only Mode* on: WaveSlice asks for the Device ID the printer shows under *Settings → Network*.
