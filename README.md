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

### Spotify

Um Spotify in der Polybar hinzuzufügen:
```
sudo pacman -S playerctl
sudo pacman -S python-pip
pip install setuptools --break-system-packages
yay -S zscroll-git
yay -S spotify
```
Füge `get_spotiyfy_status.sh` und `scroll_spotiyfy_status.sh` in `~/.config/polybar/scripts` ein.
Anschließend füge folgendes zu deiner Polybar config.ini im jeweiligen Themes Ordern von Openbox zu:
```ini
[module/spotify]
type = custom/script
tail = true
interval = 1
; prefix symbol is shown before the text
format-prefix = ""
format = <label>
exec = ~/.config/polybar/scripts/scroll_spotify_status.sh

[module/spotify-prev]
type = custom/script
exec = echo "󰒮"
format = <label>
click-left = playerctl previous -p spotify

[module/spotify-play-pause]
type = custom/ipc
hook-0 = echo ""
hook-1 = echo "<>"
initial = 1
click-left = playerctl play-pause -p spotify

[module/spotify-next]
type = custom/script
exec = echo "󰒭"
format = <label>
click-left = playerctl next -p spotify
```

### NeoVim

Die NeoVim Konfiguration liegt in [diesem Ordner](LINK), für genauere Anweisungen siehe [NeoVim Upstream](https://github.com/benbrastmckie/.config) oder das [eigene Repository](https://github.com/favo2244/NVIM_Config))
