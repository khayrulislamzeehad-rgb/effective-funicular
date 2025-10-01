Zee Dotfiles — Ultimate Anime-Themed Arch Linux Hyprland Setup
Welcome to Zee Dotfiles, a meticulously crafted, anime-inspired dotfiles repository for Arch Linux with Hyprland. This setup is designed to dazzle with its sleek, modern aesthetics and powerful functionality, perfect for ricers and Arch enthusiasts alike.
Features

Hyprland Config: Smooth animations, blur, gaps, and custom keybinds for a fluid desktop experience.
Hyprpaper Wallpaper Rotator: Dynamic, curated anime wallpapers with a systemd user service.
Alacritty Terminal: Lightweight, GPU-accelerated terminal with a polished config.
Zsh + Starship Prompt: Fast, customizable shell with an anime-themed Starship prompt.
Waybar for Hyprland: A Sway-inspired topbar with system stats and style.
Utilities: Random Uchiha clan quotes on startup and a mesmerizing fire effect script for terminal flair.
Installer: Seamless setup with symlinks to ~/.config and git integration.

Installation

Clone the repo: git clone https://github.com/khayrulislamzeehad-rgb/zee-dotfiles ~/.local/share/zee-dotfiles
Run the installer: cd ~/.local/share/zee-dotfiles && ./install.sh
Enable the wallpaper rotator: systemctl --user enable --now hyprpaper.service
Customize wallpapers in wallpapers/ and tweak configs to match your style!

Customization

Replace wallpapers in wallpapers/ with your favorite anime art.
Edit hyprland.conf, alacritty.yml, .zshrc, or starship.toml for personalized flair.
Add your own scripts to scripts/ for extra functionality.

Show off your rice on GitHub or X! ✨ “In the shinobi world, those who break the rules are scum, but those who abandon their friends are worse than scum.” — Customize and make it yours!
License
MIT License. Share, modify, and enjoy!
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
