# macOS Setup (Mojave)

A collection of configuration steps (so I don't forget them) for my macOS development environment.

## System Preferences

In **Apple Icon > System Preferences:**

- **Mouse** -> Uncheck Scroll direction: Natural
- **Security & Privacy** -> FileVault: Turn On
- **Security & Privacy** -> Firewall: Turn On

In **Finder**:

- General:
  - Show these items on the desktop: *Hard disks*
  - Change *New finder window show* to open in your *Home Directory*
- Sidebar -> Add *Home*
- Advanced -> *Show all filename extensions*

## Xcode

For installing Xcode command line tools run:

```bash
xcode-select --install
```

## Homebrew

### Installation

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Once installation is complete, run the following command to make sure everything works:

```bash
brew doctor
```

## Git

```bash
brew install git
```

Initial configuration:

```bash
git config --global user.name "Your Name Here"
git config --global user.email "your_email@youremail.com"
```

## iTerm2

Installation:

```bash
brew cask install iterm2
```

Configuration:

In **iTerm2 > Profiles:**:

- Copy Default Profile
- Window: Columns 125 / Rows: 35

## zsh & dotfiles

**Install zsh**

```bash
brew install zsh
```

**Install Oh My Zsh**

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

**Set zsh as the default terminal environment**

- Go to iTerm2 preferences.
- Profiles -> General.
- Paste /bin/zsh in the Command textbox and restart iTerm2.

**Install Powerline fonts**

```bash
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
cd ..
rm -rf fonts
```

**Dotfiles**

- [.gitconfig](https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.gitconfig)
- [.zshrc](https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.zshrc)

```bash
curl -O https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.gitconfig
curl -O https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.zshrc
````

## Applications

## Python
