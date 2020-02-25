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

**Install Powerlevel10k theme**

Installation:

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
````

Set ZSH_THEME=powerlevel10k/powerlevel10k in your ~/.zshrc.

Fonts:

Recommended: Meslo Nerd Font patched for Powerlevel10k

Download these four ttf files:

- [MesloLGS NF Regular.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Regular.ttf)
- [MesloLGS NF Bold.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Bold.ttf)
- [MesloLGS NF Italic.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Italic.ttf)
- [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Bold%20Italic.ttf)

Double-click on each file and press "Install". This will make MesloLGS NF font available to all applications on your system. Configure your terminal to use this font:

- **iTerm2**: Type p10k configure, answer Yes when asked whether to install Meslo Nerd Font and restart iTerm2 for the changes to take effect. Alternatively, open iTerm2 → Preferences → Profiles → Text and set Font to MesloLGS NF.
- **Visual Studio Code**: Open File → Preferences → Settings, enter terminal.integrated.fontFamily in the search box and set the value to MesloLGS NF.

**Dotfiles**

- [.gitconfig](https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.gitconfig)
- [.zshrc](https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.zshrc)
- [.p10k.zsh](https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.p10k.zsh)

```bash
curl -O https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.gitconfig
curl -O https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.zshrc
curl -O https://raw.githubusercontent.com/iamieht/macOS-setup/master/dotfiles/.p10k.zsh
````

## Applications

**Browsers**

- Firefox:

```bash
brew cask install firefox
```

- Chrome:

```bash
brew cask install google-chrome
```

**E-books Management**

- Calibre:

```bash
brew cask install calibre
```

## Python

**Installing pyenv**
- Build Dependencies:

```bash
brew install openssl readline sqlite3 xz zlib
```

- Using the pyenv-installer:

```bash
curl https://pyenv.run | bash
```

- Update .zshrc:

```bash
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

**Using pyenv to Install Python**
```bash
pyenv install --list
pyenv install <python_version>
```

**Using Your New Python**
```bash
pyenv versions
```

- global: The global command sets the global Python version
```bash
pyenv global <python_version>
python -m test
```

- local: The local command is often used to set an application-specific Python version
```bash
pyenv local <python_version>
```

- shell: The shell command is used to set a shell-specific Python version. This command activates the version specified by setting the PYENV_VERSION environment variable.
```bash
pyenv shell <python_version>
```
