## 🚀 Synchronizer CLI - Docker-Only Setup Guide


A minimal guide to set up and run `synchronizer-cli` using Docker. No system service installation needed.

──────────────────────────────────────────────
🛠️ Installation

Install the CLI globally:

    npm install -g synchronizer-cli

──────────────────────────────────────────────
⚙️ Quick Start

1. Initialize Configuration

This will create a config file at ~/.synchronizer-cli/config.json.

    synchronize init

Follow the prompts to enter your Synq key, wallet address, and sync name.

2. Start the Synchronizer (Docker)

After configuration, run the Docker container:

    synchronize start

✅ This automatically pulls the latest image and starts the container.

──────────────────────────────────────────────
🐳 Docker Management

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

──────────────────────────────────────────────
🧪 Platform Compatibility Test

Check if your system is compatible with Synchronizer's Docker architecture:

    synchronize test-platform

──────────────────────────────────────────────
📊 Optional: Launch Web Dashboard

This starts a temporary dashboard for real-time performance and monitoring.

    synchronize web

- Dashboard Port: 3000
- Metrics API Port: 3001

──────────────────────────────────────────────
🧰 Useful Commands

    synchronize start             Start synchronizer Docker container
    synchronize install-docker   Auto-install Docker on Linux
    synchronize fix-docker       Fix Docker permission issues
    synchronize web              Launch monitoring dashboard
    synchronize status           View status and logs

──────────────────────────────────────────────
🧾 Example Config (~/.synchronizer-cli/config.json)

```
bash
{
  "userName": "optional-sync-name",
  "key": "your-synq-key",
  "wallet": "your-wallet-address",
  "secret": "generated-secret",
  "hostname": "your-hostname",
  "syncHash": "generated-sync-hash",
  "depin": "wss://api.multisynq.io/depin",
  "launcher": "cli"
}
```

──────────────────────────────────────────────
📎 Notes

- No systemctl or background service setup required in this guide.
- Docker container will run in the foreground unless you run it in the background or with a process manager like tmux, screen, or docker run -d.
"""

# Save the guide to a text file
file_path = Path("synchronizer_docker_guide.txt")
file_path.write_text(docker_guide_text)
print(f"Guide saved to {file_path.resolve()}")

