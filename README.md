# Standard_Linux_Config
Standard linux config package list with configuration 

## 1. Packages to install
```bash
sudo pacman -S sddm qt5-graphicaleffects qt5-quickcontrols2 qt5-svg  polybar thunar obsidian vim picom rxvt-unicode unzip zsh
```
```bash
sudo yay -S brave-bin 
```

## 2. Default Resolution

```bash
cvt 1920 1080
```
Copy line ```Modeline "1920x1080_60.00"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync```

Create file ```10-mionitor.conf``` in ```/etc/X11/xorg.conf.d/``` 

```bash
sudo vim /etc/X11/xorg.conf.d/10-mionitor.conf
```
File contents
```
Section "monitor"
        Identifier "FirstMonitorOuput"
        Option "Primary" "true"
        Option "LeftOf" "SecondMonitorOutput"
        Modeline "1920x1080_60.00"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
        Option "PreferredMode" "1920x1080_60.00"
EndSection

Section "monitor2"
        Identifier "SecondMonitorOutput"
        Option "LeftOf" "FirstMonitorOutput"
        Modeline "1920x1080_60.00"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
        Option "PreferredMode" "1920x1080_60.00"
EndSection

```
## 3. i3 Configuration
Copy ```LinuxConfig/i3/config``` to ```.config/i3/config``` 

```bash
sudo cp LinuxConfig/i3/config .config/i3/config
sudo cp LinuxConfig/i3/blurelock /bin
sudo cp LinuxConfig/i3/i3exit /bin
```
Change permisions
```bash
sudo chown root:root /bin/blurelock
sudo chown root:root /bin/i3exit
sudo chmod +x /bin/blurelock
sudo chomd +x /bin/i3exit
```

## 4. Install Fonts
- Download Ubuntu Nerd Font and UbuntuMono Nerd Fornt
  
  Ubuntu Nerd Fornt: https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/Ubuntu.zip
  
  UbuntuMono Nerd Font: https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/UbuntuMono.zip
- Unzip fotns and move them to ```/usr/share/fonts/TTF/```

```bash
sudo cp Ubuntu* /usr/share/fonts/TTF/
```
## 5. Polybar Configuration
Copy ```LinuxConfig/polybar/config.ini``` to ```/etc/polybar/config.ini```

```bash
sudo cp LinuxConfig/polybar/config.ini /etc/polybar/config.ini
```

Open File and edit display name 

```bash
sudo vim /etc/polybar/config.ini
```

## 6. Default terminal

Copy ```LinuxConfig/remove.Xresources``` to ```/home/%username%/.Xresources```

```bash
sudo cp LinuxConfig/remove.Xresources /home/%username%/.Xresources
```
## 7. Picom

Copy ```LinuxConfig/picom.conf``` to ```/etc/xdg/picom.conf```

```bash
sudo cp LinuxConfig/picom.conf /etc/xdg/picom.conf
```
## 8. ZSH

Run zsh shell and generate config file

```bash
zsh
```

Run Oh-my-zsh installation script
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Copy ```LinuxConfig/gnzh.zsh-theme``` to 

```bash
sudo cp LinuxConfig/gnzh.zsh-theme /home/%username%/.oh-my-zsh/themes/gnzh.zsh-theme
```

```bash
sudo chsh -s /bin/zsh %username%
```

Edit theme name in ```.zshrc``` file.


## 9. SDDM
Copy configuration files
```bash
sudo cp -r LinuxConfig/sddm/sugar-candy /usr/share/sddm/themes/sugar-candy
sudo cp LinuxConfig/sddm/default.conf /usr/lib/sddm/sddm.config.d/default.conf
```
Change display-Manager
```bash
sudo systemctl disable lightdm
sudo systemctl enable sddm
```

## 10. Wallpaper
```bash
sudo cp /LinuxConfig/Wallpaper.jpg /usr/share/endevouros/backgrounds/endeavouros-wallpaper.png
```
