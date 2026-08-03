# PetSpawner — releases

Download and update feed for **PetSpawner**, a desktop companion app.

This repository holds **binaries only**. The application source is not here.

## Install

Grab the latest [release](https://github.com/whitecapdata/petspawner-releases/releases):

- **PetSpawner-Setup-x.y.z.exe** — installer, adds a Start menu shortcut, and
  receives automatic updates.
- **PetSpawner-x.y.z-portable.exe** — a single file, runs from anywhere.

Windows will warn about an **unknown publisher**: these builds are not yet
code-signed. If you want to be certain of what you downloaded, check it
against the `sha512` published in `latest.yml` on the same release.

## Updates

Installed copies check this repository every few hours, download in the
background, and offer a restart. Nothing installs on its own, and every
download is verified against the `sha512` in `latest.yml` before it is
staged — a file that does not match is discarded.

## Privacy

PetSpawner keeps your pets in a file on your own computer. It signs you in
with Discord so it knows whose pets are whose, and asks for the `identify`
scope only: your username and avatar, never your email, your servers, or
your messages. There is no PetSpawner server for anything to be sent to.
