# Neovim - Code Editor

![nvim2](nvim2.png)

Note 
```
In the End of this File I have Given a process To install in One Click
Using Bash File

```

### 1). Install latest neovim 


```
 sudo add-apt-repository ppa:neovim-ppa/unstable && sudo apt update && sudo apt install neovim
```

- This will install neovim 10+ version

--- 

### 2)Install Nerd font For your Laptop
##### https://www.nerdfonts.com/


---

### 3). Create a Folder then Copy The Font in that 



```
mkdir -p ~/.local/share/fonts

cp ~/Downloads/*.ttf ~/.local/share/fonts/
```


### 4)🚀 Correct Fix (Clean Install)
Step 1 — Remove broken config
```bash
rm -rf ~/.config/nvim
rm -rf ~/.local/share/nvim
rm -rf ~/.cache/nvim

```

### Step 5 — Install NVChad correctly

```bash
git clone https://github.com/NvChad/starter ~/.config/nvim
```

⚠️ Important:
Use starter repo, not the core repo.
### Step 6 — Open nvim


```bash
nvim
```

Now automatically:

- lazy.nvim install will happen
- plugins download 
- themes apply 

⏳ wait 1–2 minutes

# DONE Boom
![nvim](nvim.png)


#### To Install in One Click 
```
nano Nvm.sh
```

#### Paste This Code in File
```bash
#!/bin/bash

set -e

echo "🚀 Starting Neovim + NVChad Setup..."

# Update system
echo "📦 Updating system..."
sudo apt update

# Install dependencies
echo "📦 Installing dependencies..."
sudo apt install -y git curl unzip

# Install latest Neovim
echo "⚡ Installing Neovim 0.10+ ..."
sudo add-apt-repository -y ppa:neovim-ppa/unstable
sudo apt update
sudo apt install -y neovim

# Remove old configs
echo "🧹 Cleaning old Neovim configs..."
rm -rf ~/.config/nvim
rm -rf ~/.local/share/nvim
rm -rf ~/.cache/nvim

# Install NVChad starter
echo "📥 Installing NVChad..."
git clone https://github.com/NvChad/starter ~/.config/nvim

# Setup fonts directory
echo "🔤 Setting up Nerd Font directory..."
mkdir -p ~/.local/share/fonts

# Copy fonts if present
if ls ~/Downloads/*.ttf 1> /dev/null 2>&1; then
    cp ~/Downloads/*.ttf ~/.local/share/fonts/
    fc-cache -fv
    echo "✅ Fonts installed"
else
    echo "⚠️ No .ttf fonts found in Downloads"
fi

echo "🎉 Installation Complete!"
echo "Run Neovim with: nvim"
echo "NVChad will auto install plugins on first launch."
```

### Save and exit
Ctl +S+X

```
chmod +x Nvm.sh
```


```
./install_nvim_nvchad.sh
```



