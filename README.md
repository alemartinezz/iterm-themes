# 💻 Terminal Setup

<img width="831" alt="Screenshot 2024-02-14 at 11 42 31" src="https://github.com/alemartinezz/iterm-themes/assets/119695580/30d25acf-ac22-45b1-9ab6-259d12e4acfe">

### Homebrew

```jsx
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```jsx
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/[username]/.zprofileeval "$(/opt/homebrew/bin/brew shellenv)"
```

### iTerm2

```jsx
brew install --cask iterm2
```

### Oh My Zsh

```jsx
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### PowerLevel10K Theme for Oh My Zsh

```jsx
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

```jsx
nano ~/.zshrc
```

```jsx
ZSH_THEME = "powerlevel10k/powerlevel10k";
```

```jsx
source ~/.zshrc
```

### Meslo Nerd Font

Install the font by pressing “y” and then quit iTerm2.

### Update VSCode Terminal Font (Optional)

Open settings.json and add this line:

```jsx
"terminal.integrated.fontFamily": "MesloLGS NF"
```

### Configure PowerLevel10K

```jsx
p10k configure
```

### Increase Terminal Font Size

1. Open iTerm2 preferences
2. Go to Profiles > Text
3. I increase my font size to about 20px

### Change iTerm2 Colors to My Custom Theme

1. Open iTerm2
2. Download themes

```jsx
https://github.com/alemartinezz/iterm-themes.git
```

1. Open iTerm2 preferences
2. Go to Profiles > Colors
3. Import the downloaded color profile you want, or all.
4. Select the color profile

You can find other themes here: **[Iterm2 Color Schemes](https://iterm2colorschemes.com/)**

### Install ZSH Plugins

```jsx
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

```jsx
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

```jsx
nano ~/.zshrc
```

```jsx
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```

#### Load the new plugins

```jsx
source ~/.zshrc
```

### iTerm keybindings

1. **Open iTerm2 Preferences**: You can do this by clicking on iTerm2 in the menu bar (while iTerm2 is focused) and then selecting Preferences, or you can press `Cmd + ,` (comma) as a shortcut.

2. **Go to Profiles**: In the Preferences window, click on the Profiles tab. This is where you can configure settings that are specific to each profile. If you haven't created a custom profile yet, you'll be modifying the Default profile.

3. **Open the Keys Tab (Inside the profile)**: Within the Profiles section, find the Keys tab.

4. **Configure Key Bindings**: Click on the `+` button to add a new key binding.

#### Jump between words

- **To jump left (previous word) with Option + Left Arrow**:
  - For the input box that says "Keyboard Shortcut", press Option + Left Arrow.
  - From the "Action" dropdown, select "Send Escape Sequence".
  - In the input box that appears, type `b` (because the escape sequence for moving to the previous word in many shells like bash and zsh is `Esc-b`).
    ![[Pasted image 20240214111615.png]]
- **To jump right (next word) with Option + Right Arrow**:
  - For the input box that says "Keyboard Shortcut", press Option + Right Arrow.
  - From the "Action" dropdown, select "Send Escape Sequence".
  - In the input box that appears, type `f` (because the escape sequence for moving to the next word in many shells is `Esc-f`).

#### Delete entire word while pressing `option`

- For the "Keyboard Shortcut" field, press Option + Backspace. This might show up as `⌥←Delete` or similar, depending on your keyboard.

- In the "Action" dropdown menu, choose "Send Hex Code" or "Send Escape Sequence". The correct choice depends on your shell and iTerm2's version, but "Send Hex Code" is more universally applicable for this action.

- For "Send Hex Code", you will typically enter the hex code for deleting the word to the left of the cursor. This can vary based on the shell you are using, but a common sequence is `0x1b 0x08` (which represents `Esc + Backspace`). However, for deleting a word, a more appropriate sequence is often `0x17` which corresponds to the `^W` control character in many Unix shells that deletes the word before the cursor. If "Send Hex Code" doesn't work as expected, try "Send Escape Sequence".

- If you choose "Send Escape Sequence", you might need to enter a sequence like `d` for backward delete. However, this is less common for deleting a word backward compared to using hex codes or control characters.
