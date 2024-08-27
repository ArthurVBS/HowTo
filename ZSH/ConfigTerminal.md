# How to config zsh with oh-my-zsh and its plugins?

## Requirements

- curl
- dconf-cli
- git

## Step-by-step

### 1. Download zsh

```shell
sudo apt install zsh -y
```

### 2. Download oh-my-zsh

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### 3. Change theme

- Look for a theme & get its name

[Available Themes by Default](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

- Open the config file

```shell
sudo nano ~/.zshrc
```

- Change theme line from config file

```text
ZSH_THEME="af-magic"
```

### 4. Download zinit

- Download

```shell
bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"
```

- Self-Update

```shell
zinit self-update
```

### 5. Download zinit plugins

#### 5.1 Env Variable

- Verify if $ZSH_CUSTOM exists

```shell
cat $ZSH_CUSTOM
```

- And seems like this

```text
/home/your_user/.oh-my-zsh/custom
```

#### 5.2 Plugins

- Auto Suggestions

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

- Highlighting

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

- Syntax Highlighting

```shell
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```

- Auto Complete

```shell
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
```

#### 5.3 Apply

- Open the config file

```shell
sudo nano ~/.zshrc
```

- Change plugins line from config file

```text
plugins=(
git
  zsh-autosuggestions
  zsh-syntax-highlighting
  fast-syntax-highlighting
  zsh-autocomplete
)
```

## Extras

### 1. Use Omni Theme in the terminal

- Clone repo

```bash
git clone https://github.com/getomni/gnome-terminal.git
```

- Install

```bash
cd gnome-terminal && ./install.sh
```

- Config

> The Configuration is:
>
> - Select a color scheme: 1
> - Confirm: Yes
> - Set by Default: 1
> - Confirm: Yes
> - Dircolors Download: 1

### 2. Separate alias

- Create alias file

```shell
sudo touch .zsh_aliases
```

- Open the config file

```shell
sudo nano ~/.zshrc
```

- Add link

```text
# Alias
if [ -f ~/.zsh_aliases ]; then
    . ~/.zsh_aliases
fi
```

- Add yours alias in the alias file

```shell
sudo nano ~/.zsh_aliases
```

## Auxiliary information

- [How to apply some zinit extensions](https://youtu.be/_DQoH-YUut4?si=zb5XWKDHPOe2z6m4&t=260)
- [How to install zsh & oh-my-zsh](https://youtu.be/gn7PHkYLDZU?si=cMSilB4w-HhRsBwt)
- [How to install omni theme](https://github.com/getomni/gnome-terminal/blob/main/INSTALL.md)
