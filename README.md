# ezvol  
**ezvol** – a lightweight Bash CLI that makes Docker named‑volume backup & restore a single command away.

## ✨ Features

| Feature | What it does |
|---------|--------------|
| **Export** | Backup one or more Docker volumes (or all of them) to `*.tar` files. |
| **Import** | Restore a volume from an existing tarball; the volume is created automatically if it doesn’t exist. |



## 📦 Prerequisites

- Docker CLI installed and running (`docker` command must be available).



## 🔧 Installation

### 1️⃣ Add ~/.local/bin to PATH – one‑time setup

```bash
# Create a local bin folder if it doesn't exist
mkdir -p ~/.local/bin

# Add it to your PATH (add this line once to ~/.zshrc or ~/.bash_profile)
# For macOS or zsh
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
# For bash linux
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc

# Apply the change immediately or restart the terminal
source ~/.zshrc
```

### 2️⃣ Install `ezvol`

```bash
curl -sSL https://raw.githubusercontent.com/brandon596/ezvol/main/ezvol \
  -o ~/.local/bin/ezvol && chmod +x ~/.local/bin/ezvol
```


Now you can run `ezvol` from any directory.



## 🗑️ Uninstallation

```bash
rm ~/.local/bin/ezvol
```

(If you installed it elsewhere, adjust the path accordingly.)


## 📖 Usage

### Export a volume (or multiple)

```bash
# Single volume
ezvol export my_volume

# Multiple volumes
ezvol export vol1 vol2

# All named volumes
ezvol export -a
```

Exported files will be named `volume.tar` and placed in the current working directory.

### Import a volume

```bash
# Single tar archive
ezvol import my_volume.tar

# All tar archives in the current directory
ezvol import -a
```

The tool will create a Docker volume with the original name (if it doesn’t exist) and extract the data into it.

### Help

```bash
ezvol help
```


## ⚠️ Disclaimer

This repository is generated entirely by AI. lol  
