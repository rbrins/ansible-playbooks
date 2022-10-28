# Setup file for personal development workstation

* Currently using fedora 36 as the base OS
* dnf groupinstall "XFce Desktop"
* dnf -y install gedit
* ssh-keygen 
* installing guest addons
* dnf -y install ansible
* cd /opt && sudo git clone https://github.com/dracula/xfce4-terminal.git
* cd ~
* mkdir -p ~/.local/share/xfce4/terminal/colorschemes
* cp /opt/xfce4-terminal/Dracula.theme ~/.local/share/xfce4/terminal/colorschemes
