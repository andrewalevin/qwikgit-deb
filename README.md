# QwikGit - Git Auto-Commit and Push Script

QwikGit is a simple Bash script that automates the process of adding, committing, and pushing changes to a Git repository with a timestamp.

## Features
- Automatically commits and pushes changes
- Adds a timestamp to each commit
- Allows custom commit messages
- Includes version and help commands

## Installation

### Install from `.deb` package
1. Download the `.deb` package:
   ```bash
   wget http://yourserver.com/qwikgit-1.0.deb
   ```
2. Install the package:
   ```bash
   sudo dpkg -i qwikgit-1.0.deb
   ```
3. Verify the installation:
   ```bash
   qwikgit -h
   ```

## Usage

Run the script in a Git repository:
```bash
qwikgit "Commit message"
```

### Examples:
```bash
qwikgit                 # Auto-commit with timestamp
qwikgit "Fix bug"       # Commit with timestamp + custom message
qwikgit Fix bug and build  # Commit with timestamp + custom message (without quotes)
```

### Additional Commands
```bash
qwikgit -h, --help      # Show help information
qwikgit -v, --version   # Show version information
```

## Uninstallation
To remove the package:
```bash
sudo apt remove qwikgit
```

## Building the `.deb` Package

### 1. Prepare the Directory Structure
```bash
mkdir -p qwikgit-1.0/usr/local/bin
cd qwikgit-1.0
```

### 2. Create the Script
```bash
nano usr/local/bin/qwikgit
```
Paste the script and make it executable:
```bash
chmod +x usr/local/bin/qwikgit
```

### 3. Create `DEBIAN/control` File
```bash
mkdir DEBIAN
nano DEBIAN/control
```
Paste the following:
```
Package: qwikgit
Version: 1.0
Section: utils
Priority: optional
Architecture: all
Depends: git
Maintainer: Your Name <your.email@example.com>
Description: Simple Git auto-commit and push script
```

### 4. Build the Package
```bash
dpkg-deb --build qwikgit-1.0
```
This will generate `qwikgit-1.0.deb`.

## Publishing the Package

### Hosting on a Web Server
1. Upload `qwikgit-1.0.deb` to a web server.
2. Add this line to `/etc/apt/sources.list`:
   ```
   deb [trusted=yes] http://yourserver.com/repo ./
   ```
3. Run:
   ```bash
   sudo apt update
   sudo apt install qwikgit
   ```

### Publishing on Launchpad (PPA)
To distribute the package to Ubuntu users, consider creating a PPA on [Launchpad](https://launchpad.net/).

## License
This project is licensed under the MIT License.

