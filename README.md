# dotfiles

Personal dotfiles for Arch Linux running [Omarchy](https://omarchy.org/) (Hyprland + Wayland).

Managed with [GNU Stow](https://www.gnu.org/software/stow/).

## System

| Component | Tool |
|-----------|------|
| OS | Arch Linux |
| Desktop | Omarchy (Hyprland) |
| Shell | Zsh + Starship |
| Terminal | Ghostty / Kitty / Foot |
| Editor | Neovim |
| Launcher | Walker (+ Rofi fallback) |
| Bar | Waybar |
| File manager | Oil.nvim / Nautilus |
| Multiplexer | Tmux |
| Theme | Catppuccin Mocha |

## Installation

```bash
# Install GNU Stow
sudo pacman -S stow

# Clone the repo
git clone https://github.com/domabyte/dotfiles.git ~/dotfiles
cd ~/dotfiles

# Stow everything at once
stow alacritty btop elephant environment fastfetch \
     fontconfig foot ghostty git hyprland hyprlock \
     hyprmocha hyprpaper imv kitty lazygit mise \
     nvim opencode rofi shell spicetify starship \
     swayosd tmux uwsm voxtype walker waybar \
     wiremix zshrc

# Or stow individual packages
stow hyprland
stow waybar
stow zshrc
```

## Structure

Each directory is a [Stow package](https://www.gnu.org/software/stow/) — it mirrors the target filesystem from `$HOME`.

```
dotfiles/
├── alacritty/        → ~/.config/alacritty/
├── backgrounds/      → ~/.config/backgrounds/    (wallpapers)
├── btop/             → ~/.config/btop/            (system monitor)
├── elephant/         → ~/.config/elephant/        (walker extensions)
├── environment/      → ~/.config/environment.d/   (fcitx, env vars)
├── fastfetch/        → ~/.config/fastfetch/       (system info display)
├── fontconfig/       → ~/.config/fontconfig/      (font rendering)
├── foot/             → ~/.config/foot/            (foot terminal)
├── ghostty/          → ~/.config/ghostty/         (ghostty terminal)
├── git/              → ~/.config/git/             (git config + ignore)
├── hyprland/         → ~/.config/hypr/            (hyprland WM)
├── hyprlock/         → ~/.config/hypr/            (lock screen)
├── hyprmocha/        → ~/.config/hypr/            (catppuccin mocha colors)
├── hyprpaper/        → ~/.config/hypr/            (wallpaper)
├── imv/              → ~/.config/imv/             (image viewer)
├── kitty/            → ~/.config/kitty/           (kitty terminal)
├── lazygit/          → ~/.config/lazygit/         (git TUI)
├── mise/             → ~/.config/mise/            (dev tool manager: node, python)
├── nvim/             → ~/.config/nvim/            (neovim config)
├── opencode/         → ~/.config/opencode/        (opencode AI)
├── rofi/             → ~/.config/rofi/            (app launcher fallback)
├── shell/            → ~/                         (.bash_profile, .profile, .XCompose)
├── spicetify/        → ~/.config/spicetify/       (Spotify customization)
├── starship/         → ~/.config/starship.toml    (shell prompt)
├── swayosd/          → ~/.config/swayosd/         (on-screen volume/brightness display)
├── tmux/             → ~/.config/tmux/            (tmux + catppuccin + tpm)
├── uwsm/             → ~/.config/uwsm/            (Wayland session manager)
├── voxtype/          → ~/.config/voxtype/         (voice-to-text transcription)
├── walker/           → ~/.config/walker/          (app launcher)
├── waybar/           → ~/.config/waybar/          (status bar)
├── wiremix/          → ~/.config/wiremix/         (PipeWire audio mixer)
└── zshrc/            → ~/                         (.zshrc)
```

## Neovim

Full plugin list and keybindings are documented in [`nvim/.config/nvim/KEYBINDINGS.md`](nvim/.config/nvim/KEYBINDINGS.md).

Also lives at its own repo: [domabyte/Neovim-config](https://github.com/domabyte/Neovim-config)

## Shell

`.zshrc` includes:
- `starship` prompt
- `zoxide` for smart `cd`
- `fzf` key bindings + completion
- `mise` for dev tool management (node, python)
- `tm` alias — fuzzy tmux session picker via zoxide
- `cat` → `bat`, `ls` → `lsd -a`

## Wallpapers

Wallpapers live in `backgrounds/.config/backgrounds/`. Set via Omarchy:

```bash
omarchy theme bg next       # cycle wallpaper
omarchy theme bg set <path> # set specific
```
