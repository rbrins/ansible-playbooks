# Setup file for personal development workstation

### General Updates, Permissions, and Configurations
* Currently using fedora 36 as the base OS
* dnf -y update
* ssh-keygen 
* installing guest addons
* sudo usermod --append --groups vboxsf $USER
* restart???
* cp .ssh/id_rsa.pub /media/sf_shared

### Adding Applications
* dnf -y install gedit ansible docker stack haskell-platform
* dnf -y groupinstall "Development Tools"

### Themes & Apperance
XFce Desktop is really only needed for VMs, the default gnome should work just fine with gtk themes right? 
* dnf groupinstall "XFce Desktop"
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
#### Dracula gedit
* wget https://raw.githubusercontent.com/dracula/gedit/master/dracula.xml
* mkdir -p ~/.local/share/gedit/styles
* mv dracula.xml ~/.local/share/gedit/styles/
* rm dracula.xml

### Install Homebrew
* /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
* echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /home/russell/.bash_profile
* echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/russell/.bash_profile
* eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"

TODOs:
* add xfce4 terminal config and preference file
* clean up of themes? or standardize of updates with git pulls?
* Currently need to manually enable the installed themes, icons, and backgrounds, would like to change that automatically
* Add launcher apps automatically to the panel 
* Considering text editor from dc864 meeting for normal editing
