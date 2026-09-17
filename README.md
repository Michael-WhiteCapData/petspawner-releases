# PetSpawner — releases

A desktop companion app: spawn, collect and look at pixel-art dogs, and keep one on your desktop
while you work.

## Download

**[→ Go to the latest release](https://github.com/Michael-WhiteCapData/petspawner-releases/releases/latest)**
and pick your file from the table at the top of it:

| Platform | File | |
| --- | --- | --- |
| **Windows** 10/11 | `PetSpawner-Setup-x.y.z.exe` | installer, updates itself |
| **Windows** portable | `PetSpawner-x.y.z-portable.exe` | one file, no install |
| **macOS** Apple Silicon | `PetSpawner-x.y.z-arm64.dmg` | M1 and later |
| **macOS** Intel | `PetSpawner-x.y.z-x64.dmg` | pre-2021 Macs |

Not sure which Mac you have? Apple menu → About This Mac. "Apple M1/M2/M3/M4" means Apple Silicon.

Every release page carries the same table with direct links, so you can click straight through. Only
the current version is downloadable; older releases stay listed as a history of what changed.

## Before you run it

Neither build is code-signed, so each operating system will complain the first time.

**Windows** shows "unknown publisher" — click *More info* → *Run anyway*.

**macOS** says the app *"is damaged and can't be opened"*. It is not damaged — the download is
fine, and each release lists a SHA-256 you can check. That is what macOS says about apps without a
paid Apple Developer signature.

Right-click → Open used to get past this and **no longer works on macOS 15 and later**. What works
today:

```
xattr -dr com.apple.quarantine /Applications/PetSpawner.app
```

Then open it normally. If running that is not something you want to do, this build is not yet for
you — a paid Apple Developer ID is the proper fix and it is on the list.

If you want to verify what you downloaded, every release lists a SHA-256 for each file, and
`latest.yml` carries a SHA-512 for the Windows installer.

## Updates

**Windows updates itself.** The app checks in the background, verifies the download, and offers a
restart. Nothing is installed without you clicking, and nothing restarts behind your back.

**macOS does not**, because Apple refuses to apply updates to unsigned apps. PetSpawner on a Mac
does not even check — it will not sit downloading something it can never install. Come back here
when a new version appears; your pets are stored separately and survive replacing the app.

## How updates are verified

Every release carries a `signed-manifest.json` signed with a private key that never leaves the
developer's machine. Installed copies refuse any update whose manifest is missing or does not
verify — so even someone who took over this repository could not push code to an installed app.

## Privacy

PetSpawner keeps your pets in a file on your own computer. It signs you in with Discord so it knows
whose pets are whose, and asks for the `identify` scope only: your username and avatar, never your
email, your servers, or your messages. There is no PetSpawner server for anything to be sent to.

---

This repository holds **binaries only**. The application source is not here.
