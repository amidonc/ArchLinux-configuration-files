# Install Yay
```
cd /opt
sudo git clone https://aur.archlinux.org/yay.git  
sudo chown -R <username>:users ./yay
cd yay
makepkg -si
```

# update archlinux
```
yay -Syu
```

# set default shell of new user to zsh
```
chsh -s /bin/zsh
```

# check and install missing firmwares
```
mkinitcpio -p linux
```
shows 'Possibly missing firmware for module: '
such as aic94xx-firmware & wd719x-firmware

search yay and install the firmwares
```
yay -Ss aic94xx
yay -Si aic94xx-firmware
```

# OPENSSL key
```
ssh-keygen -t ed25519 -C "email@example.com"
eval "$(ssh-agent -s)"
```
  $> Agent pid 59566
```
ssh-add ~/.ssh/id_ed25519
```

# permissions
  700	~/.shh	
  644	~/.ssh/authorized_keys
  644	~/.ssh/known_hosts
  644	~/.ssh/config
  600	~/.ssh/id_rsa
  644	~/.ssh/id_rsa.pub
          
# link xterm to foot - for rofu running terminal apps
```
ln -s /bin/foot /bin/xterm
```








# OH-MY-ZSH
download & install oh-my-zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
   
download & configure powerlevel10k
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
   
      change the value of ZSH_THEME in ~/.zshrc
      ZSH_THEME="powerlevel10k/powerlevel10k"
         
configure pl10k:
p10k configure
         
      clone plugins:
         zsh-syntax-highlighting
            git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
         zsh-autosuggestions
            git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
         
	activate the plugins:
            in ~/.zshrc add plugins to plugins=() line.
               plugins=( git zsh-syntax-highlighting zsh-autosuggestions)


# bootstrap blackarch
   curl -O https://blackarch.org/strap.sh
   
   set execute bit
      chmod +x strap.sh
   run strap.sh
      sudo ./strap.sh
   enable multilib following https://wiki.archlinux.org/index.php/Official_repositories#Enabling_multilib and run
      sudo pacman -Syu
 
 