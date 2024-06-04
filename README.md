# Archcraft-Dotfiles

## Installation
Installier Archcraft von diesem [Link](https://archcraft.io/) und boote Iso-Datei.

Wenn Archcraft gebootet hat, wähle `Launch Calamaries` und folge den Anweisungen.

Wenn Archcraft fertig installiert ist, führe folgenden Kommandos aus:
```
sudo pacman -Syyu
sudo pacman -S debugedit
sudo pacman -S archlinux-keyring
sudo pacman-key --init
sudo pacman-key --populate
```

## Configuration

Um Spotify in der Polybar hinzuzufügen, führe `Spotify.install` aus. Die NeoVim Konfiguration liegt in [diesem Ordner](LINK), für genauere Anweisungen siehe [NeoVim Upstream](https://github.com/benbrastmckie/.config) oder das [eigene Repository](https://github.com/favo2244/NVIM_Config))
