# 🌸 Zee Dotfiles — Ultimate Anime-Themed Arch Linux Hyprland Setup 🌸

<p align="center">
  <img src="https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/wallpapers/sample.jpg" alt="Anime Wallpaper" width="300"/>
  <br>
  <em>Welcome to a stunning, anime-inspired desktop experience!</em>
</p>

Welcome to **Zee Dotfiles**, a meticulously crafted, anime-inspired dotfiles repository for Arch Linux with Hyprland. This setup blends sleek, modern aesthetics with powerful functionality, perfect for ricers and Arch enthusiasts alike. ✨

---

## 🚀 Features

| Feature                | Description                                      |
|------------------------|--------------------------------------------------|
| **Hyprland Config**    | Smooth animations, blur, gaps, custom keybinds   |
| **Hyprpaper Rotator**  | Dynamic anime wallpapers with systemd service    |
| **Alacritty Terminal** | Lightweight, GPU-accelerated terminal            |
| **Zsh + Starship**     | Fast shell with anime-themed prompt              |
| **Waybar for Hyprland**| Sway-inspired topbar with system stats           |
| **Utilities**          | Uchiha quotes & fire effect scripts              |
| **Installer**          | Seamless setup with `~/.config` symlinks          |

---

## 🎮 Installation

Get started with a single command to install and set up your Zee Dotfiles effortlessly:

- **One-Command Installation**  
  ```bash
  bash -c "$(curl -sL https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/install.sh)" && cd ~/.local/share/zee-dotfiles && ./install.sh
  
  📋 Important Notes
  - This command downloads and runs the installer from GitHub.
  - **Prompt**: Type `y` and press Enter to proceed.
  - **Internet**: Ensure an active connection.
  - **Dependencies**: Install first with:
    ```bash
    sudo pacman -S git curl hyprland hyprpaper alacritty zsh starship waybar
    ```
  - **Safety Check**: Review the script:
    ```bash
    curl -sL https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/install.sh > install.sh
    less install.sh
    ```
  

Enable Wallpaper Rotator
bashsystemctl --user enable --now hyprpaper.service

Customize Your Setup

Add anime wallpapers to ~/.local/share/zee-dotfiles/wallpapers/.
Edit configs (e.g., hyprland.conf, alacritty.yml) to personalize.




🎨 Customization

Wallpapers: Replace wallpapers/ with your favorite anime art.
Configs: Tweak hyprland.conf, alacritty.yml, .zshrc, or starship.toml.
Scripts: Add your own to scripts/ for extra flair.


  <img src="https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/sample-screenshot.jpg" alt="Sample Setup" width="400">
  

  Showcase your unique rice! 🌟


🌐 Show Off Your Rice
Share your setup on GitHub or X!
“In the shinobi world, those who break the rules are scum, but those who abandon their friends are worse than scum.” — Make it yours! ✨
📜 License
MIT License — Share, modify, and enjoy!
