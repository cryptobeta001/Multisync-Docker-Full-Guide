## 🚀 Synchronizer CLI - Docker-Only Setup Guide

A minimal guide to set up and run `synchronizer-cli` using Docker. No system service installation needed.

---
## 🛠️ Installation

UFW unlock

    Sudo ufw allow 3000/tcp
    Sudo ufw allow 3001/tcp

Check the new rule:

    Sudo ufw status

Install the CLI globally:

    npm install -g synchronizer-cli

---
## ⚙️ Quick Start

1. Initialize Configuration

This will create a config file at ~/.synchronizer-cli/config.json.

    synchronize init
    

Follow the prompts to enter your Synq key, wallet address, and sync name.

---
## 🐳 Docker Management

Install Docker (Linux only):

    synchronize install-docker

This auto-installs Docker and handles:
- Docker daemon setup
- docker group permissions
- Cross-distro support (Ubuntu, Debian, CentOS, RHEL, Fedora)

Fix Docker Permissions:

If you see permission errors:

    synchronize fix-docker

Log out and back in afterward for changes to take effect.

---

## 📊 Setup-Service file

    synchronize service
    sudo cp ~/.synchronizer-cli/synchronizer-cli.service /etc/systemd/system/
    sudo systemctl daemon-reload
    sudo systemctl enable synchronizer-cli
    sudo systemctl start synchronizer-cli

## Web Dashboard

    synchronize service-web
    sudo cp ~/.synchronizer-cli/synchronizer-cli-web.service /etc/systemd/system/
    sudo systemctl daemon-reload
    sudo systemctl enable synchronizer-cli-web
    sudo systemctl start synchronizer-cli-web

## To check logs

    journalctl -u synchronizer-cli -f 
    
---
## 🧰 Useful Commands

| Command                      | Description                                                               |
| ---------------------------- | ------------------------------------------------------------------------- |
| `synchronize start`          | Launch the Docker container. Auto-detects platform & checks Docker setup. |
| `synchronize status`         | Display current service state, logs, and helpful next steps.              |
| `synchronize web`            | Launch the web dashboard for live monitoring.                             |
| `synchronize install-docker` | Install Docker automatically (Linux only). Supports major distros.        |
| `synchronize fix-docker`     | Fix Docker group permissions & user access.                               |
| `synchronize test-platform`  | Validate Docker compatibility with your system architecture.              |
    
---

## 📎 Notes

- No systemctl or background service setup required in this guide.
- Docker container will run in the foreground unless you run it in the background or with a process manager like tmux, screen, or docker run -d.
"""

---
