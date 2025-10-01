# Zee Dotfiles — Ultimate Anime-Themed Arch Linux Hyprland Setup

Welcome to **Zee Dotfiles**, a meticulously crafted, anime-inspired dotfiles repository for Arch Linux with Hyprland. This setup is designed to dazzle with its sleek, modern aesthetics and powerful functionality, perfect for ricers and Arch enthusiasts alike.

## Features
- **Hyprland Config**: Smooth animations, blur, gaps, and custom keybinds for a fluid desktop experience.
- **Hyprpaper Wallpaper Rotator**: Dynamic, curated anime wallpapers with a systemd user service.
- **Alacritty Terminal**: Lightweight, GPU-accelerated terminal with a polished config.
- **Zsh + Starship Prompt**: Fast, customizable shell with an anime-themed Starship prompt.
- **Waybar for Hyprland**: A Sway-inspired topbar with system stats and style.
- **Utilities**: Random Uchiha clan quotes on startup and a mesmerizing fire effect script for terminal flair.
- **Installer**: Seamless setup with symlinks to `~/.config` and git integration.

## Installation
Get started with a single command to install and set up your Zee Dotfiles effortlessly:

- **One-Command Installation**
  ```bash
  bash -c "$(curl -sL https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/install.sh)" && cd ~/.local/share/zee-dotfiles && ./install.sh


Important Notes:

This command will download and run the installer script directly from GitHub.
The script will prompt for confirmation. Type y and press Enter to proceed.
Ensure you have an active internet connection.
Install required dependencies beforehand with:
textsudo pacman -S git curl hyprland hyprpaper alacritty zsh starship waybar

For safety, you can first download and review the script:
textcurl -sL https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/install.sh > install.sh
less install.sh

Step 2: Enable the Wallpaper Rotator
textsystemctl --user enable --now hyprpaper.service

Step 3: Customize Your Setup

Add your favorite anime wallpapers to the ~/.local/share/zee-dotfiles/wallpapers/ directory.
Edit configuration files (e.g., ~/.local/share/zee-dotfiles/hypr/hyprland.conf, ~/.local/share/zee-dotfiles/alacritty/alacritty.yml) to personalize.



Customization

Replace wallpapers in wallpapers/ with your favorite anime art.
Edit hyprland.conf, alacritty.yml, .zshrc, or starship.toml for personalized flair.
Add your own scripts to scripts/ for extra functionality.
