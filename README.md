# 🍷 Qwik Git - Git Auto-Commit & Push with Timestamp

Qwik Git (`qw`) is a simple Bash script that automates git commit and push operations with a timestamp. Now available for Ubuntu as a **Debian package** via a **Personal Package Archive (PPA)**.


[https://launchpad.net/qwikgit](https://launchpad.net/qwikgit)



## 📦 Installation via PPA

### 1️⃣ Add the PPA
```bash
sudo add-apt-repository ppa:andrewalevin/qwikgit
sudo apt update
```

### 2️⃣ Install Qwik Git
```bash
sudo apt install qwikgit
```

### 3️⃣ Usage

#### Auto-commit with timestamp
```bash
qw
```

#### Auto-commit with timestamp + custom message
```bash
qw Fix bug in authentication
```
*(No need for quotes around the commit message!)*

#### Show version
```bash
qw --version
```

#### Show help
```bash
qw --help
```

---

## 🛠 Notes for Developers (Publishing a New Version)

### 1️⃣ Prepare the Source Package
On an Ubuntu machine, install required tools:
```bash
sudo apt update && sudo apt install devscripts debhelper build-essential
```

### 2️⃣ Create Debian Packaging Files
Inside the project folder (`qwikgit`), create a `debian` directory:
```bash
mkdir -p qwikgit/debian
cd qwikgit/debian
```

#### **Create `control` file**
```bash
nano control
```
Paste this:
```
Source: qwikgit
Maintainer: Your Name <your@email.com>
Section: utils
Priority: optional
Standards-Version: 4.5.0
Build-Depends: debhelper (>= 12)

Package: qwikgit
Architecture: all
Depends: git
Description: Git auto-commit and push with timestamp
 A simple Bash script to auto-commit and push Git repositories with a timestamp.
```

#### **Other Required Files**
```bash
nano rules      # Add build rules
nano changelog  # Add version changes
nano copyright  # Specify license
nano install    # Define installation paths
```

### 3️⃣ Build the Package
```bash
debuild -S -sa
```

### 4️⃣ Upload to PPA
```bash
dput ppa:andrewalevin/qwikgit qwikgit_1.2-0ubuntu1_source.changes
```

### 5️⃣ Wait for Launchpad to Build and Publish
Monitor build status at: [Launchpad PPA](https://launchpad.net/~andrewalevin/+archive/ubuntu/qwikgit)

Once published, users can install using:
```bash
sudo add-apt-repository ppa:andrewalevin/qwikgit
sudo apt update
sudo apt install qwikgit
```

---

## 📜 License
**MIT License** - Use freely under open-source terms.

---

## 🌟 Contributing
Feel free to submit issues or pull requests on GitHub!

**GitHub Repository:** [QwikGit on GitHub](https://github.com/andrewalevin/qwikgit)

---

🚀 Happy coding with Qwik Git! 🎉

