# kubeterm-bin

Arch Linux package for [Kubeterm](https://github.com/kbterm/kubeterm), repackaged from the upstream `.deb`.

## Install

```sh
git clone https://github.com/<user>/kubeterm-bin.git
cd kubeterm-bin
makepkg -si
```

## Update

```sh
git pull
makepkg -si
```

## Uninstall

```sh
sudo pacman -Rns kubeterm-bin
```

## Dependencies

- `gtk3`
- `libsecret`
- `libepoxy`
- `xdg-utils`

## Automation

`.github/workflows/update.yml` checks upstream daily, bumps `pkgver`, resets `pkgrel`, regenerates `sha256sums` and `.SRCINFO`, and commits the change.
