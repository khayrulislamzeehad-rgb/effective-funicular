🌸 Zee Dotfiles — Ultimate Anime-Themed Arch Linux Hyprland Setup 🌸

  <img src="https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/wallpapers/sample.jpg" alt="Anime Wallpaper" width="300">
  

  Welcome to a stunning, anime-inspired desktop experience!

Welcome to Zee Dotfiles, a meticulously crafted, anime-inspired dotfiles repository for Arch Linux with Hyprland. This setup blends sleek, modern aesthetics with powerful functionality, perfect for ricers and Arch enthusiasts alike. ✨

🚀 Features





































FeatureDescriptionHyprland ConfigSmooth animations, blur, gaps, custom keybindsHyprpaper RotatorDynamic anime wallpapers with systemd serviceAlacritty TerminalLightweight, GPU-accelerated terminalZsh + StarshipFast shell with anime-themed promptWaybar for HyprlandSway-inspired topbar with system statsUtilitiesUchiha quotes & fire effect scriptsInstallerSeamless setup with ~/.config symlinks

🎮 Installation
Get started with a single command to install and set up your Zee Dotfiles effortlessly:

One-Command Installation
bashbash -c "$(curl -sL https://raw.githubusercontent.com/khayrulislamzeehad-rgb/zee-dotfiles/main/install.sh)" && cd ~/.local/share/zee-dotfiles && ./install.sh

📋 Important Notes
- This command downloads and runs the installer automatically.
- **No Manual Input Required**: The script proceeds without needing 'y' confirmation.
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
EOF

























Write sample Hyprland config
write_file "hypr/hyprland.conf" <<'EOF'
Zee Dotfiles: Hyprland Config
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
Write sample Alacritty config
write_file "alacritty/alacritty.yml" <<'EOF'
Zee Dotfiles: Alacritty Config
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
Write sample Zsh config
write_file "zsh/.zshrc" <<'EOF'
Zee Dotfiles: Zsh Config
eval "$(starship init zsh)"
source ~/.local/share/zee-dotfiles/scripts/random_quote.sh
alias ls='ls --color=auto'
EOF
Write sample Starship config
write_file "starship.toml" <<'EOF'
Zee Dotfiles: Starship Prompt
format = """
[$username@](bg:#ff4444 fg:#000000) [$directory](bg:#1a1b26 fg:#c0caf5) $git_branch
$character"""
[username]
show_always = true
format = "$user"
EOF
Write sample Hyprpaper service
write_file "systemd/user/hyprpaper.service" <<'EOF'
[Unit]
Description=Zee Dotfiles Hyprpaper Wallpaper Rotator
After=graphical-session.target
[Service]
ExecStart=/usr/bin/hyprpaper
Restart=always
[Install]
WantedBy=graphical-session.target
EOF
Write sample script for random Uchiha quotes
write_file "scripts/random_quote.sh" <<'EOF'
#!/bin/bash
Zee Dotfiles: Random Uchiha Quote
quotes=(
"In the shinobi world, those who break the rules are scum..."
"Power is not will, it is the phenomenon of physically making things happen."
"The people of this clan are all the same. You focus on the trivial..."
)
echo "${quotes[$RANDOM % ${#quotes[@]}]}"
EOF
chmod +x "$DOTFILES_DIR/scripts/random_quote.sh"
Write sample fire effect script (placeholder)
write_file "scripts/fire_effect.sh" <<'EOF'
#!/bin/bash
Zee Dotfiles: Terminal Fire Effect (Placeholder)
echo "🔥 Simulating a blazing terminal effect! 🔥"
Add actual fire effect logic (e.g., using 'aafire' or custom animation)
EOF
chmod +x "$DOTFILES_DIR/scripts/fire_effect.sh"
Write sample wallpaper directory
mkdir -p "$DOTFILES_DIR/wallpapers"
print_info "Created wallpapers directory. Add your anime wallpapers to $DOTFILES_DIR/wallpapers/"
Create symlinks
symlink_config "hypr/hyprland.conf"
symlink_config "alacritty/alacritty.yml"
symlink_config "zsh/.zshrc"
symlink_config "starship.toml"
symlink_config "systemd/user/hyprpaper.service"
Write USAGE.txt
write_file "USAGE.txt" <<'EOF'
Zee Dotfiles Usage


Ensure dependencies: hyprland, hyprpaper, alacritty, zsh, starship, waybar


Add wallpapers to wallpapers/


Run install.sh to symlink configs


Enable hyprpaper: systemctl --user enable --now hyprpaper.service


Customize configs in ~/.local/share/zee-dotfiles
EOF
Write FINISH.txt
write_file "FINISH.txt" <<'EOF'


Zee Dotfiles Installation Complete!
Your anime-themed Hyprland setup is ready! ✨
Next steps:


Add wallpapers to ~/.local/share/zee-dotfiles/wallpapers/


Tweak configs in ~/.local/share/zee-dotfiles


Run systemctl --user enable --now hyprpaper.service for wallpaper rotation


Share your rice on GitHub or X!
"Those who do not understand true pain can never understand true peace." — Enjoy your setup!
EOF
Finalize
print_info "🎉 Installation complete! Check $DOTFILES_DIR/FINISH.txt for next steps."
print_info "🔥 'The true measure of a shinobi is not how he lives, but how he dies.' — Show off your rice! 🔥"
}
