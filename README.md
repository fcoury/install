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

## Install mac apps & fonts
```
brew cask install                 \
1password                         \
astrill                           \
atom                              \
cloudapp                          \
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
spotify                           \
textexpander                      \
trickster
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
git config --global alias.co "checkout"
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

## Misc TODOs

- [ ] Enable all controls on Tabs `System Preferences` > `Keyboard` > `Shortcuts` > `All controls`
- [ ] Fix resolution to `Scaled` on `System Preferences` > `Display` (for MacBook Pro)
- [ ] Disable QUIC in Chrome - [http://kb.fortinet.com/kb/documentLink.do?externalID=FD36680](link)
- [ ] Configure Dropbox
  - [ ] Open Dropbox app and login
  - [ ] Pause syncing
  - [ ] Copy an existing `~/Dropbox` folder from a source (ie, `rsync -azvh 'mbp.local:~/Dropbox' .`)
  - [ ] Resume syncing
