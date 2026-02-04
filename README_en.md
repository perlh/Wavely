
# Wavely — Nuclei POC Manager & Vulnerability Validation Tool


🔍 A localized POC management and vulnerability validation platform for security researchers.

- Supports custom templates, batch scanning, packet capture & debugging, global request headers, and more to help verify and reproduce vulnerabilities more efficiently.

![main](imgs/3.2.8/3.png)
![main](imgs/3.2.8/2.png)

For detailed installation and activation, see: Wavely Official Wiki: https://github.com/perlh/Wavely/wiki

Features
- POC template management: create/read/update/delete templates, import with deduplication (by Template ID)
- Multi-task scanning: run multiple POCs against multiple targets in bulk; tasks can be stopped manually
- Request analysis & debugging: full request/response view, built-in packet capture, HTTP request replay
- Editor experience: theme switch, font size, YAML linting, raw auto-parse
- Advanced settings: custom DNSLog, scan rate control, HTTP/HTTPS/SOCKS5 proxies, request timeouts
- Search & filter: keyword search, filter by tag/author, advanced search and reload
- Import & export: drag-and-drop import of YAML/POC folders, batch export, export scan reports (xlsx, docx)
- Persistence: user settings auto-saved across restarts
- API testing: scan endpoints and paths
- Progress & results: visual progress, exportable results
- Cross-platform: macOS and Windows supported; Linux under testing

Recent updates

- v3.2.9 — Latest

	✨ Added

	- Toolbox module: integrated subnet calculator and common encoding/decoding tools (Base64, Hex, URL).
	- License import: support importing license files.
	- Internationalization: default support for Simplified Chinese and English; switchable in Settings.

	🔍 Improvements

	- Request details: view all requests/responses triggered by a matched POC for deeper analysis.
	- Packet size: show request/response byte sizes in the capture tool.
	- UI & interactions: overall style and flows refined for smoother UX.
	- Add request replay in the POC editor module.

	🐞 Fixed

	- Duplicate results: fixed duplicate scan result entries when a single POC contains multiple requests.

- v3.2.8: added author-based grouping filter; POC search supports multiple keywords; HTTP request replay supported
- v3.2.7: added DSL/Binary/Size matching and multiple extractors (regex/json/kval); tag-based grouping filter; request timeout setting

1. Installation

MacOS (Install / Update)
- Drag Wavely.app into the Applications folder
- Remove macOS quarantine attribute if needed:

```bash
sudo xattr -d com.apple.quarantine /Applications/Wavely.app
```

Windows (Install / Update)
- Download and extract the latest archive
- Run `Wavely-windows-installer.exe` to complete installation

2. Usage

Activation
- Refer to the official activation guide:
	Wavely Activation Guide: https://github.com/perlh/Wavely/wiki

License file locations after activation:

| Platform | Path |
|---|---|
| macOS / Linux | ~/.wavely/license |
| Windows | same folder as Wavely.exe |

Notes:
- Upgrading: overwrite the existing app with the new installer rather than uninstalling to avoid losing the license file (v3.2.6+ has relaxed restrictions).

DNSLog
- Default: Nuclei official Interactsh service (no extra config needed)
- To use a private DNSLog, follow Interactsh deployment docs: https://github.com/projectdiscovery/interactsh

3. Basic operations

POC import: drag a folder containing POCs into the main window to import in bulk.

POC add / edit / capture tools / request replay / global headers — see screenshots in the repository `imgs/` folder.

4. FAQ & Troubleshooting

- Windows: brief command window on startup is normal.
- macOS: if the app won't open due to unsigned binaries, try removing quarantine or fixing executable permission:

```bash
sudo xattr -d com.apple.quarantine /Applications/Wavely.app
chmod 755 /Applications/Wavely.app/Contents/MacOS/Wavely
```

Disclaimer

This tool is intended for authorized enterprise security testing only. Do not use it against unauthorized targets. The repository's POCs are for theoretical validation and do not include exploit chains. Ensure compliance with local laws and obtain permission before scanning targets.

Support
- Project: https://github.com/perlh/Wavely
- Feedback & activation issues: id_0909186@foxmail.com

