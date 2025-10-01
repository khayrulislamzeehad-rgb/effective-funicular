🌸 Zee Dotfiles 🌸

  <img src="https://raw.githubusercontent.com/zeehadhaque/zee-dotfiles/main/wallpapers/sample.jpg" alt="Anime Wallpaper" width="300">
  

  A stunning anime-themed Arch Linux Hyprland setup!

Welcome to Zee Dotfiles, crafted by zeehadhaque, an anime-inspired dotfiles repo for Arch Linux with Hyprland. Enjoy sleek aesthetics and powerful features! ✨

🚀 Features





































FeatureDescriptionHyprland ConfigAnimations, blur, gaps, custom keybindsHyprpaper RotatorDynamic anime wallpapers with serviceAlacritty TerminalLightweight, GPU-accelerated terminalZsh + StarshipFast shell with anime promptWaybarSway-inspired topbar for HyprlandUtilitiesUchiha quotes, fire effect scriptsInstallerAuto setup with ~/.config symlinks

🎮 Installation
Install with one command:

One-Command Setup
bashbash -c "$(curl -sL https://raw.githubusercontent.com/zeehadhaque/zee-dotfiles/main/install.sh)" && cd ~/.local/share/zee-dotfiles && ./install.sh

📋 Notes
- Runs automatically, no 'y' input needed.
- Requires internet and dependencies:
  ```bash
  sudo pacman -S git curl hyprland hyprpaper alacritty zsh starship waybar
  ```
- Safety: Review script first:
  ```bash
  curl -sL https://raw.githubusercontent.com/zeehadhaque/zee-dotfiles/main/install.sh > install.sh
  less install.sh
  ```


Enable Wallpaper
bashsystemctl --user enable --now hyprpaper.service

Customize

Add wallpapers to ~/.local/share/zee-dotfiles/wallpapers/.
Edit hyprland.conf, alacritty.yml, etc.




🎨 Customization

Swap wallpapers/ with your anime art.
Tweak configs in ~/.local/share/zee-dotfiles.
Add scripts to scripts/.


  <img src="https://raw.githubusercontent.com/zeehadhaque/zee-dotfiles/main/sample-screenshot.jpg" alt="Setup Preview" width="400">
  

  Show your rice! 🌟


🌐 Share Your Rice
Post on GitHub or X!
“Those who break rules are scum, but abandoning friends is worse.” — Make it yours! ✨
📜 License
MIT
EOF
Write configs
write_file "hypr/hyprland.conf" <<'EOF'
Hyprland Config by zeehadhaque
monitor=,preferred,auto,1
exec-once=hyprpaper & waybar & random_quote.sh
input {
kb_layout=us
follow_mouse=1
}
general {
gaps_in=5
gaps_out=10
border_size=2
col.active_border=rgb(ff4444) rgb(00ff00) 45deg
}
animation {
windows=1
windowsIn=1
fade=1
}
EOF
write_file "alacritty/alacritty.yml" <<'EOF'
Alacritty Config by zeehadhaque
font:
normal:
family: JetBrainsMono
style: Regular
size: 12
colors:
primary:
background: '#1a1b26'
foreground: '#c0caf5'
EOF
write_file "zsh/.zshrc" <<'EOF'
Zsh Config by zeehadhaque
eval "$(starship init zsh)"
source ~/.local/share/zee-dotfiles/scripts/random_quote.sh
alias ls='ls --color=auto'
EOF
write_file "starship.toml" <<'EOF'
Starship Config by zeehadhaque
format = """
[$username@](bg:#ff4444 fg:#000000) [$directory](bg:#1a1b26 fg:#c0caf5) $git_branch
$character"""
[username]
show_always = true
format = "$user"
EOF
write_file "systemd/user/hyprpaper.service" <<'EOF'
[Unit]
Description=Hyprpaper Wallpaper Rotator by zeehadhaque
After=graphical-session.target
[Service]
ExecStart=/usr/bin/hyprpaper
Restart=always
[Install]
WantedBy=graphical-session.target
EOF
Write scripts
write_file "scripts/random_quote.sh" <<'EOF'
#!/bin/bash
Random Quote by zeehadhaque
quotes=("In the shinobi world, those who break rules are scum..."
"Power is not will, it is making things happen."
"This clan focuses on the trivial...")
echo "${quotes[$RANDOM % ${#quotes[@]}]}"
EOF
chmod +x "$DOTFILES_DIR/scripts/random_quote.sh"
write_file "scripts/fire_effect.sh" <<'EOF'
#!/bin/bash
Fire Effect by zeehadhaque
echo "🔥 Blazing terminal effect! 🔥"
EOF
chmod +x "$DOTFILES_DIR/scripts/fire_effect.sh"
Create wallpapers dir
mkdir -p "$DOTFILES_DIR/wallpapers"
print_info "Add anime wallpapers to $DOTFILES_DIR/wallpapers/"
Symlink configs
symlink_config "hypr/hyprland.conf"
symlink_config "alacritty/alacritty.yml"
symlink_config "zsh/.zshrc"
symlink_config "starship.toml"
symlink_config "systemd/user/hyprpaper.service"
Write usage
write_file "USAGE.txt" <<'EOF'
Usage by zeehadhaque


Install dependencies: sudo pacman -S hyprland hyprpaper alacritty zsh starship waybar


Add wallpapers to wallpapers/


Run install.sh


Enable hyprpaper: systemctl --user enable --now hyprpaper.service


Customize in ~/.local/share/zee-dotfiles
EOF
write_file "FINISH.txt" <<'EOF'


Installation Complete by zeehadhaque
Setup ready! ✨


Add wallpapers to ~/.local/share/zee-dotfiles/wallpapers/


Edit configs in ~/.local/share/zee-dotfiles


Enable wallpaper: systemctl --user enable --now hyprpaper.service


Share on GitHub/X!
EOF
print_info "🎉 Setup complete! Check $DOTFILES_DIR/FINISH.txt."
print_info "🔥 Show off your rice! 🔥"
}
