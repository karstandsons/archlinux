# Karst & Sons package repository for Arch Linux

Signed pacman packages for Arch, CachyOS, Omarchy and other Arch-based systems,
served at https://karstandsons.github.io/archlinux.

| Package | What |
|---|---|
| `darkmatter` | [Darkmatter](https://github.com/karstandsons/darkmatter), an Omarchy-themed Mattermost client |

## Set up (once)

Trust the signing key, then add the repository:

```sh
curl -sL https://karstandsons.github.io/archlinux/karstandsons.asc | sudo pacman-key --add -
sudo pacman-key --lsign-key 21F3F82B682C36A4F3576168D033CB9918675079
printf '\n[karstandsons]\nServer = https://karstandsons.github.io/archlinux/$arch\n' | sudo tee -a /etc/pacman.conf
```

Signing key: **Karst & Sons Packages** `21F3 F82B 682C 36A4 F357  6168 D033 CB99 1867 5079`

## Install and update

```sh
sudo pacman -Sy darkmatter
sudo pacman -Syu        # updates arrive with the rest of your system
```

To remove the repository, delete the `[karstandsons]` section from
`/etc/pacman.conf`.

Packages here are built and signed by each project's release workflow. The
`main` branch holds this README and the key; the site (`gh-pages`) holds
only the current packages.
