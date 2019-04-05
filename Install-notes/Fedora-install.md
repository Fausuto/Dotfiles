# Gettings Started

### System Update
First update package manager after installing.
```
$ dnf update
```

### Install necessary packages
```
$ dnf install -y xdg-user-dirs @base-x bspwm sxhkd dmenu rxvt-unicode-256color neovim firefox nnn htop neofetch feh wget curl git
```

### Setup default directories
```
$ xdg-user-dirs-update
```

### Setup for bspwm
```
$ mkdir -p ~/.config/{bspwm,sxhkd}
$ cp /usr/share/doc/bspwm/examples/bspwmrc ~/.config/bspwm/
$ cp /usr/share/doc/bspwm/examples/sxhkdrc ~/.config/sxhkd/
$ chmod u+x ~/.config/bspwm/bspwmrc
```

If you don't want too many .serverauth files from starting up `startx`, in the home dir

```
$ sudo nvim /usr/bin/startx
# xserverauthfile=$XAUTHORITY
```

# VirtualBox Guest Additions Installation

### Install packages
```
$ dnf install -y dkms binutils gcc make cmake automake patch libgomp glibc-headers glibc-devel kernel-headers kernel-devel bzip2 perl
```

### Install Firefox
```
$ dnf install firefox
# download latest "Guest Additions" from www.virtualbox.org/wiki/Testbuild
```

### Install Guest Additions
```
$ sudo mkdir /media/VirtualBoxGuestAdditions
$ sudo mount /path/to/downloaded/file /media/VirtualBoxGuestAdditions
$ cd /media/VirtualBoxGuestAdditions
$ sudo ./VBoxLinuxAdditions.run
$ reboot
```

# ZSH Setup

### Install zsh and zsh-syntax-highlighting
```
$ dnf install -y zsh zsh-syntax-highlighting
```

### Install oh-my-zsh
#### via wget
```
$ sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

### Install zsh-autosuggestions
```
$ git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
```

### Edit .zshrc
```
$ nvim .zshrc
source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
```

### Reload .zshrc
```
$ source ~/.zshrc
```

### alias to reload .Xresources
```
alias xup="xrdb ~/.Xresources"
```

# Fonts

### Install Terminus Fonts
```
# Through package manager
$ dnf install -y terminus-fonts
```

### Install Iosevka
```
# Download from https://github.com/be5invis/Iosevka/releases
$ unzip /path/to/file -d /path/to/dir/
$ sudo cp -r /path/to/dir/ /usr/share/fonts/
```
