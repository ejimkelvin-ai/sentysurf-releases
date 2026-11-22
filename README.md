# SentySurf

**Free security monitor for Windows.** SentySurf checks your PC's security settings, warns you about
scams and suspicious changes, and can keep an eye on your family's computers. It is read-only: it never
changes, deletes or ends anything unless you click a button that clearly says so.

## Download

Get the newest version from **[Releases](../../releases/latest)**:

| Your PC | File to download |
|---|---|
| Most PCs (Intel or AMD processor) | `SentySurf-Setup-<version>.exe` |
| ARM PCs (e.g. Snapdragon / Copilot+ laptops) | `SentySurf-Setup-<version>-arm64.exe` |

Not sure which you have? Open **Settings → System → About** and look at **System type**.
"ARM-based processor" means you need the `-arm64` file.

After installing, SentySurf updates itself: it checks once a day and you install updates from
**Settings → Updates** inside the app.

## Requirements

- Windows 10 (version 1809 or newer) or Windows 11
- 64-bit Windows (x64 or ARM64)
- An administrator account to install (other accounts on the PC are protected too)

## If the installer won't start

**"Windows protected your PC" (blue screen)** – SentySurf isn't code-signed yet. Click **More info →
Run anyway**.

**"Smart App Control blocked an app"** – On PCs with Smart App Control turned on, Windows blocks apps
that aren't code-signed, and there's no way to allow a single app. SentySurf can't run on these PCs
until it's signed. (You can turn Smart App Control off in Windows Security → App & browser control,
but it can't always be turned back on, so think carefully before doing that.)

**Nothing happens / "This app can't run on your PC"** – The PC may be in **Windows S mode**, which only
allows Microsoft Store apps. SentySurf doesn't support S mode.

**Your antivirus quarantines it** – Some antivirus products wrongly flag new, unsigned apps. Check the
file against `SHA256SUMS.txt` in the release, then restore it or add an exception in your antivirus.

**Work or school computer** – Your IT department's rules may block installing apps. Ask them first.

## Check your download

Each release includes `SHA256SUMS.txt`. In PowerShell, in the folder with the download:

```
Get-FileHash .\SentySurf-Setup-<version>.exe
```

The hash should match the line for that file in `SHA256SUMS.txt`.

## Privacy

SentySurf runs entirely on your PC with no account and no tracking. It only goes online to check for
updates (once a day, from this page), when you use the password check (only part of a one-way
fingerprint of the password is sent), and during scans to ask Windows' winget tool about app updates.
Family mode shares a short security summary, end-to-end encrypted with your family code, through the ntfy.sh relay (an optional shared folder can be used too).

---
© 2026 Kelvin. SentySurf is free for personal use. It complements, but does not replace, antivirus software.
