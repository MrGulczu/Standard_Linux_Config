# Standard_Linux_Config
Standard linux config package list with configuration 

## 1. Packages to install
```bash
sudo pacman -S --needed sddm qt5‑graphicaleffects qt5‑quickcontrols2 qt5‑svg polybar thunar obsidian vim picom rxvt-unicode unzip
```
```bash
sudo yay -S brave-bin 
```
## 2. i3 Configuration
Copy ```LinuxConfig\i3\config``` to ```.config\i3\config``` 

## 3. install Font
- Download Ubuntu Nerd Font and UbuntuMono Nerd Fornt
  
  Ubuntu Nerd Fornt: https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/Ubuntu.zip
  
  UbuntuMono Nerd Font: https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/UbuntuMono.zip
- Unzip fotns and move them to ```\usr\share\fonts\TTF\```

## 4. Polybar Configuration
Copy ```LinuxConfig\polybar\config.ini``` to ```\etc\polybar\config.ini```

Open File and edit display name 

## 5. Default terminal

Copy ```LinuxConfig\remove.Xresources``` to ```\home\%username%\.Xresources```

## 6. Picom

Copy ```LinuxConfig\picom.conf``` to ```\etc\xdg\picom.conf```
