# rename-applications

A small Zenity-based utility for creating per-user desktop-entry overrides,
so application names can be changed in the launcher without modifying files
owned by system packages.

This utility is designed primarily for the Omarchy desktop environment. It
uses the standard `.desktop` application entries and should also work on
other desktop environments that use them. After a rename, it attempts to run
`omarchy menu refresh`; that refresh is optional and is safely ignored when
Omarchy is not installed.

No specific Omarchy version is pinned. The utility is intended for current
Omarchy installations and relies on the `omarchy menu refresh` command when
available.

## Build locally

From this directory:

```bash
makepkg -si
```

Required runtime packages are `bash`, `zenity`, and `desktop-file-utils`.
The `omarchy` command is optional; when present, it refreshes the Omarchy
launcher immediately after a rename.

## Publish to the AUR

1. Create a public GitHub repository named `rename-applications`.
2. Replace `REPLACE_ME` in `PKGBUILD` with your GitHub username.
3. Put this directory's files in the repository and commit them.
4. Create a GitHub release named `v1.0.0` and upload a source archive named
   `rename-applications-1.0.0.tar.gz`.
5. Update `sha256sums` in `PKGBUILD` with the archive checksum.
6. Clone your AUR package repository and copy in `PKGBUILD`.
7. Run `makepkg --printsrcinfo > .SRCINFO`, commit both files, and push.

The AUR package repository URL is:

```text
ssh://aur@aur.archlinux.org/rename-applications.git
```

## Preserve renamed entries

The package installs the utility, not personal rename choices. Those choices
are user-owned desktop files under:

```text
~/.local/share/applications/
```

Back up that directory separately if the renamed entries must follow you to
another system.
