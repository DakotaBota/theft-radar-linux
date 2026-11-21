# TheftRadar on Linux — store publishing pack

App: opens https://theftradar.pro in a dedicated Chromium app window. Works with any Chromium-family browser; falls back to xdg-open.

## Snap (Ubuntu / any snapd distro)
1. `snapcraft login` (Ubuntu One — browser flow)
2. `snapcraft register theft-radar` (one-time; or claim via dashboard.snapcraft.io)
3. Upload with CI: push this repo to GitHub → https://build.snapcraft.io → enable build → artifact auto-uploads on completion
   - or locally if snapcraft installed: `snapcraft pack` → `snapcraft upload --release=stable theft-radar_1.0.0.snap`
4. Store listing: dashboard.snapcraft.io → metadata → screenshot + description (use README copy below)

## AUR (Arch)
1. Create account: aur.archlinux.org/register
2. `git clone ssh://aur@aur.archlinux.org/theft-radar.git` (creates repo on first push if it doesn't exist)
3. Copy PKGBUILD + .SRCINFO into it, then:
   `git add . && git commit -m "initial import: theft-radar 1.0.0" && git push`

## Flathub (optional, slow review)
1. Fork https://github.com/flathub/flathub, add `com.theftid.TheftRadar.json` at repo root
2. PR to flathub/new-first-party? For new apps: submit via https://github.com/flathub/flathub PR with the manifest
3. Review ~1-2 weeks; app id `pro.theftradar.TheftRadar` (or com.theftradar.TheftRadar)

## Store description copy (reuse everywhere)
SHORT: Report stolen items free. National register, theft map, neighborhood alerts, evidence packets.
FULL: What do you do when something gets stolen? TheftRadar gives every victim free, immediate tools: file a report into a public national register, search serials before buying secondhand, track matches on a live map, get alerts, and hand police a professional evidence packet. Installing opens TheftRadar as a dedicated app window on your desktop.

## Assets in this repo
- snapcraft.yaml + theft-radar-snap + theft-radar.desktop + theft-radar.png (Snap)
- ../aur/PKGBUILD + .SRCINFO (AUR)
- ../flatpak/com.theftid.TheftRadar.json (Flathub)
- ../theft-radar.deb (Debian family direct download; also served at https://theftradar.pro/downloads/theft-radar.deb)
