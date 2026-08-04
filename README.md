# PetSpawner — releases

Download and update feed for **PetSpawner**, a desktop companion app.

This repository holds **binaries only**. The application source is not here.

Get the latest build from [Releases](https://github.com/whitecapdata/petspawner-releases/releases).
Older versions stay listed as a history; only the current one is downloadable.

## Windows

**PetSpawner-Setup-x.y.z.exe** — installs for your user only, adds a Start
menu shortcut, and updates itself. **PetSpawner-x.y.z-portable.exe** is a
single file that runs from anywhere and does not update itself.

Windows will warn about an **unknown publisher**: these builds are not
code-signed. If you want to be certain of what you downloaded, check it
against the `sha512` in `latest.yml` on the same release.

Updates arrive on their own — the app checks in the background, verifies the
download, and offers a restart. Nothing installs without you clicking.

## macOS

Two builds, and you need the right one:

- **PetSpawner-x.y.z-arm64.dmg** — Apple Silicon (M1, M2, M3, M4; any Mac from
  late 2020 onward)
- **PetSpawner-x.y.z-x64.dmg** — Intel Macs

### macOS will say the app "is damaged"

It is not damaged. That is the message macOS shows for **any** app that has
not been signed with a paid Apple Developer certificate, and it is the same
message it would show for a genuinely broken download, which is unhelpful of
it.

To open it: **right-click the app → Open → Open**. You only do this once; it
launches normally afterwards.

### Mac builds do not update themselves

macOS refuses to apply updates to unsigned apps, so PetSpawner on a Mac does
not check for them at all — it will not sit there downloading things it can
never install. When a new version appears here, download it and replace the
old one. Your pets are stored separately and survive.

Both limitations are the same missing thing: an Apple Developer ID. Windows
has no equivalent requirement, which is why Windows updates work.

## How updates are verified

Every release carries a `signed-manifest.json` signed with a private key that
never leaves the developer's machine. Installed copies refuse any update whose
manifest is missing or does not verify — so even someone who took over this
repository could not push code to an installed app.

## Privacy

PetSpawner keeps your pets in a file on your own computer. It signs you in
with Discord so it knows whose pets are whose, and asks for the `identify`
scope only: your username and avatar, never your email, your servers, or your
messages. There is no PetSpawner server for anything to be sent to.
