# mare-rio pacman repository

Signed Arch Linux packages from mare-rio. It holds `reef`, a reading-first Markdown reader and editor.

## Add the repository

```sh
curl -fsSL https://mare-rio.github.io/pacman/mare-rio.asc | sudo pacman-key --add -
sudo pacman-key --lsign-key 2615D08710F426A092E92F8277B7F9A185A4311F
printf '\n[mare-rio]\nServer = https://mare-rio.github.io/pacman/$arch\n' | sudo tee -a /etc/pacman.conf
sudo pacman -Sy reef
```

Upgrades arrive with `pacman -Syu`. Signing key: `2615D08710F426A092E92F8277B7F9A185A4311F`
("mare-rio packages (pacman repository signing key)").

## How it is published

GitHub Pages serves the `gh-pages` branch. Each package's release workflow builds the package, signs it
and the database with the key above, and force-pushes a single commit holding the whole site, with the
three newest builds of each package. `main` holds only this page.
