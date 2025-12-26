# ezvol  
**ezvol** – a lightweight Bash CLI that makes Docker named‑volume backup & restore a single command away.

## ✨ Features

| Feature | What it does |
|---------|--------------|
| **Export** | Backup one or more Docker volumes (or all of them) to `*.tar.gz` files. |
| **Import** | Restore a volume from an existing tarball; the volume is created automatically if it doesn’t exist. |



## 📦 Prerequisites

- Docker CLI installed and running (`docker` command must be available).



## 🔧 Installation

### 1️⃣ macOS – one‑time setup (Linux users can skip)

```bash
# Create a local bin folder if it doesn't exist
mkdir -p ~/.local/bin

# Add it to your PATH (add this line once to ~/.zshrc or ~/.bash_profile)
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc

# Apply the change immediately
source ~/.zshrc
```

### 2️⃣ Install `ezvol`

```bash
curl -sSL https://raw.githubusercontent.com/brandon596/ezvol/main/ezvol \
  -o ~/.local/bin/ezvol && chmod +x ~/.local/bin/ezvol
```
Alternative shortened URL:

```bash
curl -sSL https://tini.fyi/13gBe \
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

Exported files will be named `volume.tar.gz` and placed in the current working directory.

### Import a volume

```bash
# Single tarball
ezvol import my_volume.tar.gz

# All tarballs in the current directory
ezvol import -a
```

The tool will create a Docker volume with the original name (if it doesn’t exist) and extract the data into it.

### Help

```bash
ezvol help
```


## ⚠️ Disclaimer

This repository is generated entirely by AI. lol  
