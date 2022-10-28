# Setup file for personal development workstation

* Currently using fedora 36 as the base OS
* dnf -y update
* dnf groupinstall "XFce Desktop"
* dnf -y install gedit
* ssh-keygen 
* installing guest addons
* dnf -y install ansible

### Themes & Apperance
#### Dracula theme for xfce4 terminal 
* cd /opt && sudo git clone https://github.com/dracula/xfce4-terminal.git
* cd ~
* mkdir -p ~/.local/share/xfce4/terminal/colorschemes
* cp /opt/xfce4-terminal/Dracula.theme ~/.local/share/xfce4/terminal/colorschemes
#### Dracula theme for xfce4 (through gtk)
* wget https://github.com/dracula/gtk/archive/master.zip 
* mkdir -p ~/.themes
* unzip master.zip -d ~/.themes
* mv ~/.themes/gtk-master ~/.themes/Dracula
* gsettings set org.gnome.desktop.interface gtk-theme "Dracula"
* gsettings set org.gnome.desktop.wm.preferences theme "Dracula"
* rm master.zip
#### Dracula icons
* wget https://github.com/dracula/gtk/files/5214870/Dracula.zip
* mkdir -p ~/.icons
* unzip Dracular.zip -d ~/.icons
* gsettings set org.gnome.desktop.interface icon-theme "Dracula"
* rm Dracula.zip
#### Dracula wallpaper
* wget https://github.com/dracula/wallpaper/archive/master.zip
* unzip master.zip
* sudo mv wallpaper-master/fedora.png /usr/share/backgrounds/images
* rm master.zip


TODOs:
* add xfce4 terminal config and preference file
* clean up of themes? or standardize of updates with git pulls?
* Currently need to manually enable the installed themes, icons, and backgrounds, would like to change that automatically
