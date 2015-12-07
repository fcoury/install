# Fresh install script

## Install oh my zsh

```
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
```

## Install Homebrew

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Install command line tools

```
brew install \
ack          \
fswatch      \
hub          \
go           \
node         \
python       \
rbenv        \
ruby-build   \
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
brew tap caskroom/fonts
```

## Add dev/beta versions
```
brew tap caskroom/versions
```

### Add dupes
```
brew tap homebrew/dupes
```

### Install mac apps & fonts
```
brew cask install                 \
1password                         \
astrill                           \
atom                              \
cloudapp                          \
daisydisk                         \
divvy                             \
firefox                           \
font-inconsolata-dz-for-powerline \
font-inconsolata-g-for-powerline  \
font-inconsolata-lgc              \
gitter                            \
google-chrome                     \
istat-menus                       \
iterm2-beta                       \
laullon-gitx                      \
launchbar                         \
mailplane                         \
marked                            \
sizeup                            \
slack                             \
skitch                            \
spotify                           \
textexpander                      \
textmate                          \
trickster                         \
vagrant                           \
virtualbox
```

### Replace OpenSSL
```
brew install openssh --with-brewed-openssl --with-keychain-support
```

## Git

### Setup GitHub and Git config values

```
git config --global user.name "Felipe Coury"            && \
git config --global user.email "felipe.coury@gmail.com" && \
git config --global github.user fcoury                  && \
git config --global core.editor "atom -w"               && \
git config --global color.ui true                       && \
git config --global push.default simple                 && \
git config --global alias.st "status -sb"               && \
git config --global alias.co "checkout"                 && \
git config --global pull.rebase true
```

## Atom

### Install sync package

```
apm install sync-settings
```

### Add sync options

**IMPORTANT:** Remember to change `<TOKEN>` below:

```
cat <<EOS >> ~/.atom/config.cson
  "sync-settings":
    personalAccessToken: "<TOKEN>"
    gistId: "123bcb643391d340bd3b"
EOS
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

- [ ] Enable all controls on Tabs `System Preferences` > `Keyboard` > `Shortcuts` > `All controls`
- [ ] Fix resolution to `Scaled` on `System Preferences` > `Display` (for MacBook Pro)
- [ ] Show volume menu item - `System Preferences` > `Sound` > `Show volume in menu bar`
- [ ] Enable feedback when volume is changed - `System Preferences` > `Sound` > `Play feedback when volume is changed`

### Google Chrome

- [ ] Disable QUIC in Chrome - [link](http://kb.fortinet.com/kb/documentLink.do?externalID=FD36680)

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

### TextExpander

- [ ] `Preferences` > check `Launch at Login`
- [ ] `Preferences` > uncheck `Show main window at launch`
- [ ] `Preferences` > `Sync`
  - [ ] click `Link to Snippets...`
  - [ ] choose `~/Dropbox/TextExpander/Settings.textexpandersettings`
- Add license

### Launchbar

- [ ] Add brew cask applications
  - [ ] `Index` > `Show Index`
  - [ ] Select the `Options` tab (righthand side)
  - [ ] Click `+` > Select `/opt/homebrew-cask/Caskroom`
- [ ] Expand clipboard capacity
  - [ ] `Preferences` > `Clipboard` > `Capacity`
  - [ ] Change to `100 items`
- [ ] Open at login
  - [ ] Right click the dock icon
  - [ ] Select `Options` > `Open at login`
- [ ] Hide dock icon
  - [ ] `Preferences` > `Advanced`
  - [ ] Uncheck `Show Dock Icon`

### Licenses

- [ ] Decrypt LICENSES.md - `openssl enc -d -aes-256-cbc -in LICENSES.md.enc -out LICENSES.md`
