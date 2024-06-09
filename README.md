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

Allgemeine nützliche packages:

```
sudo pacman -S zathura
sudo pacman -S thunderbird
sudo pacman -S discord
sudo pacman -S gimp
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

Folge den Anweisungen aus dem Repository [.config](https://github.com/favo2244/.config).
Wichtig ist hierbei (Stand 06/2024) nicht die neuste Neovim Version zu nutzen, sondern die version `0.9.x`.

Dazu sind folgende Schritte (in Arch Linux) nötig:
- `sudo pacman -S base-devel cmake unzip ninja tree-sitter curl`
- Nun muss der alte Branch aus dem Nvim Repo kopiert werden, z.B. `release-0.9`
  
  `git clone -b release-0.9 https://github.com/neovim/neovim.git`
- `cd neovim`
- `make CMAKE_BUILD_TYPE=RelWithDebInfo`
- `sudo make install`

Anschließend sollte Neovim installiert sein und kann über `nvim` aufgerufen werden.

Weitere Packages die für NeoVim in dieser Konfiguration installiert sein sollten:
```
sudo pacman -S zathura
sudo pacman -S npm
sudo npm install -g neovim
sudo pacman -S ripgrep
sudo pacman -S latexmk
sudo pacman -S fd
sudo pacman -S biber
sudo pacman -S ruby
gem install neovim
sudo pacman -S wget
sudo pacman -S go
sudo pacman -S php
sudo pacman -S jdk-openjdk
sudo pacman -S julia
sudo pacman -S cargo
sudo pacman -S composer
sudo pacman -S luarocks
sudo pacman -S perl
sudo pacman -S zathura-pdf-mupdf
```
Für zathura muss die entsprechende `zathurarc` in `~/.config/zathura` 

Für die gesamten Dotfiles zu erhalten, kopiere den Ordner `nvim` nach `~/.config/nvim`

Hinweis: die eigenen Dotfiles stammen aus [diesem Repository](https://github.com/favo2244/NVIM_Config), welches aus dem [geforkten Repository](https://github.com/favo2244/.config) hervorgeht. Dieses sollte stets synchron mit dem [Upstream](https://github.com/benbrastmckie/.config) sein.
Für weitere Infos siehe [hier](https://github.com/favo2244/NVIM_Config).


### Jupyter

Um Jupyter-Notebook zu installieren und auszuführen:

```
sudo pacman -S jupyter-notebook
jupyter notebook
```

Um Jupyter-Notebook zu installieren und auszuführen:

```
sudo pacman -S jupyterlab
jupyter lab
```

Nützliche packages:

```
pip install scipy --break-system-packages
pip install numpy --break-system-packages
pip install sympy --break-system-packages
pip install matplotlib --break-system-packages
```
