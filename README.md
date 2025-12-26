# ezvol
**ezvol** is a lightweight Bash CLI tool designed to simplify the management of Docker named volumes. It automates the process of exporting volumes to tarballs and importing them back, using ephemeral `busybox` containers to ensure a clean and consistent state.
## Features
- **Export Volumes**: Easily backup specific Docker named volumes or all of them at once.
- **Import Volumes**: Restore volumes from tarballs with automatic volume creation.
- **Clean Execution**: Uses temporary `busybox` containers that are removed immediately after the operation, leaving no clutter.
- **Smart Naming**: Automatically handles file naming conventions (appending `_ezvol.tar.gz` on export and stripping it on import).
## Prerequisites
- **Docker**: The tool requires the Docker CLI to be installed and running.
## Installation
1.  Download the `ezvol` script.
2.  Make the script executable:
    ```bash
    chmod +x ezvol
    ```
3.  (Optional) Move it to a directory in your `$PATH` for global usage:
    ```bash
    sudo mv ezvol /usr/local/bin/ezvol
    ```
## Usage
### Exporting Volumes
To export one or more specific volumes:
```bash
ezvol export my_volume another_volume
```
This will create `my_volume_ezvol.tar.gz` and `another_volume_ezvol.tar.gz` in the current directory.
To export **ALL** named volumes:
```bash
ezvol export -a
```
### Importing Volumes
To import one or more specific tarballs:
```bash
ezvol import my_volume_ezvol.tar.gz
```
This will create a docker volume named `my_volume` (if it doesn't exist) and restore the data.
To import **ALL** tarballs (`*.tar.gz`) in the current directory:
```bash
ezvol import -a
```
### Help
Display the help menu:
```bash
ezvol help
```
## How It Works
- **Export**: Mounts the requested volume and the current directory into a temporary `busybox` container, then runs `tar czf` to create a compressed archive of the volume's contents.
- **Import**: Creates the destination volume (if missing), mounts it and the current directory into a temporary `busybox` container, and runs `tar xzf` to extract the archive into the volume.

## Disclaimer
This repository is completely AI-generated using Anitgravity lol
