# Fresh install script

## Install oh my zsh

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Install ZSH plugins

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

## Install Homebrew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install command line tools

```
brew install \
svn          \
ack          \
fswatch      \
hub          \
graphviz     \
go           \
jq           \
node         \
python       \
ssh-copy-id  \
tree         \
wget
```

## Vim

```
brew install vim --with-python --with-ruby --with-perl
```

## Add font support to Homebrew
```
brew tap homebrew/cask-fonts
```

## Install fonts

```
brew install font-fira-code                    \
             font-inconsolata-g-for-powerline  \
             font-inconsolata-lgc              \
```

### Add dupes
```
brew tap homebrew/dupes
```

### Replace OpenSSL
```
brew install openssh
```

## Git

### Setup GitHub and Git config values

```
git config --global user.name "Felipe Coury"            && \
git config --global user.email "felipe.coury@gmail.com" && \
git config --global github.user fcoury                  && \
git config --global core.editor "code --wait"           && \
git config --global color.ui true                       && \
git config --global push.default simple                 && \
git config --global pull.rebase false                   && \
git config --global alias.st "status -sb"               && \
git config --global alias.co "checkout"
```

### Setup hub

```
touch ~/.config/hub
```

Create a Personal Access Token on GitHub and create a file with the following content:

```
github.com:
 - user: fcoury
   oauth_token: PASTE_YOUR_TOKEN_HERE
   protocol: https
```

## Dotfiles

### zsh

```
cd ~
git clone git@github.com:fcoury/dotzsh.git .zsh
ln -s .zsh/zshrc .zshrc
```

### vim

```
cd ~
git clone git@github.com:fcoury/dotvim.git .vim
ln -s .vim/vimrc .vimrc

cd ~/.vim
git submodule init
git submodule update

vim +PluginInstall +qall
```

## LICENSES.md

### Encrypt

```
openssl enc -aes-256-cbc -salt -in LICENSES.md -out LICENSES.md.enc
```

### Decrypt

```
openssl enc -d -aes-256-cbc -in LICENSES.md.enc -out LICENSES.md
```

## Misc TODOs

### Mac OS X

- [ ] Enable all controls on Tabs `System Preferences` > `Keyboard` > `Shortcuts` > `Use keyboard navigation...`
- [ ] Fix resolution to `Scaled` on `System Preferences` > `Display` (for MacBook Pro)
- [ ] Show volume menu item - `System Preferences` > `Sound` > `Show volume in menu bar`
- [ ] Enable feedback when volume is changed - `System Preferences` > `Sound` > `Play feedback when volume is changed`

### Dropbox

- [ ] Configure Dropbox
  - [ ] Open Dropbox app and login
  - [ ] Pause syncing
  - [ ] Copy an existing `~/Dropbox` folder from a source (ie, `rsync -azvh 'mbp.local:~/Dropbox' .`)
  - [ ] Resume syncing

### iTerm

- [ ] Add color themes to iTerm2 - [mbadolato/iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)
  - [ ] Go to `Preferences` > `Profiles` > select `Default` > `Colors` > `Import`
  - [ ] Import all Tomorrow themes from `~/code/iTerm2-Color-Schemes`
  - [ ] Select `Tomorrow Night` from dropdown
  - [ ] Go to `Preferences` > `Text`
  - [ ] Change font to `14pt Inconsolata-g for Powerline`

### Licenses

- [ ] Decrypt LICENSES.md - `openssl enc -d -aes-256-cbc -in LICENSES.md.enc -out LICENSES.md`
