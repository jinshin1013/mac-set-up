# mac-set-up

Set of things I do when setting up a new mac

These are the applications I use daily:

1. iTerm2
2. Zen Browser
3. VSCode, Cursor AI
4. RayCast
5. Proton Pass

### 1. oh-my-zsh setup

Setting up omz is quite easy.

#### Install Oh My Zsh

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

#### Configure omz

Open `~/.zshrc` to modify `ZSH_THEME=agnoster`

```sh
ZSH_THEME="agnoster"
```

#### Install Powerline Fonts

```sh
# clone
git clone https://github.com/powerline/fonts.git --depth=1
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```

then configure `Font` in iTerm2 to `Meslo LG M DZ for Powerline`.

#### Install omz plugins

```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

then add the plugin to the list of plugins in `~/.zshrc`.

```sh
plugins=(
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
)
```

then run `source ~/.zshrc`

### 2. Install Brew

Run the following command to install brew.

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then add this to `~/.zprofile`

```sh
eval "$(/opt/homebrew/bin/brew shellenv)"
```

### 3. Install nvm

Run the following command to install nvm.

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
```

Then add this to `~/.zprofile`

```sh
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

### 4. Android stuff

After install Android Studio, add the following to `~/.zshrc`

```sh
export ANDROID_HOME=/Users/${username}/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/platform-tools
export JAVA_HOME=/Applications/Android\ Studio.app/Contents/jbr/Contents/Home
```

### 5. Set up VSCode / Cursor AI

Install the following extensions: `Eslint`, `Expo Tools`, `GitLens`, `Prettier`, `Tokyo Night`, `vscode-icons`, `Svelte`.

Then install `Fira Code` fonts (get the font from their github).

Add the following settings:

```json
{
  "workbench.iconTheme": "vscode-icons",
  "workbench.startupEditor": "none",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "always"
  },
  "editor.tabSize": 2,
  "editor.fontFamily": "'Fira Code'",
  "editor.fontLigatures": true,
  "workbench.colorTheme": "Tokyo Night"
}
```
