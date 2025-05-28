# 🚀 Docker-Only Guide for `synchronizer-cli`

A minimal, systemd-free approach to running `synchronizer-cli` using Docker.

---

## 📦 Install `synchronizer-cli`

Open your terminal and run:

```bash
npm install -g synchronizer-cli
```

---

## ⚙️ Initialize Configuration

Set up your configuration interactively:

```bash
synchronize init
```

### 📁 Example `config.json` (nano config.json)

```json
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

---

## ▶️ Start the Synchronizer

Run the synchronizer Docker container:

```bash
synchronize start
```

##🔄 Run in the Background

```bash
nohup synchronize start > sync.log 2>&1 &
```
This will:
Start the synchronizer in the background
Redirect logs to sync.log
Keep it running even after you close the terminal

---

## 📊 Check Service Status & Performance

View the service status and recent logs:

```bash
synchronize status
```

---

## 🌐 Launch Web Dashboard

Start the performance monitoring dashboard:

```bash
synchronize web
```

---

## 📘 Commands Reference (Docker-Focused)

| Command                      | Description                                                               |
| ---------------------------- | ------------------------------------------------------------------------- |
| `synchronize start`          | Launch the Docker container. Auto-detects platform & checks Docker setup. |
| `synchronize status`         | Display current service state, logs, and helpful next steps.              |
| `synchronize web`            | Launch the web dashboard for live monitoring.                             |
| `synchronize install-docker` | Install Docker automatically (Linux only). Supports major distros.        |
| `synchronize fix-docker`     | Fix Docker group permissions & user access.                               |
| `synchronize test-platform`  | Validate Docker compatibility with your system architecture.              |

---

## 🖥️ Web Dashboard Features

![image](https://github.com/user-attachments/assets/26033195-33ec-433a-a935-ba3db4456147)

### 📈 Performance Metrics

* **Total Traffic:** Shows data in smart format (KB / MB / GB).
* **Active Sessions:** Tracks number of live sessions.
* **Traffic Rate:** Displays inbound/outbound bytes per second.
* **User Count:** Monitors connected users in real time.

### ✅ Quality of Service (QoS)

* **Overall Score:** Circular indicator with color-coded grades.
* **Reliability, Availability, Efficiency** breakdown.

### 🔌 API Documentation
