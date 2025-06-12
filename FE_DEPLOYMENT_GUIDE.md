# Frontend Deployment Guide

This guide provides instructions for deploying two frontend applications: `token-ban-player` and `token-streaming-system`.

## Prerequisites

- Ubuntu/Debian server with sudo access
- Git installed
- Internet connection

## Initial Setup

### 1. Install Node.js

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
```

Verify installation:

```bash
node --version
npm --version
```

### 2. Install PM2 Process Manager

```bash
sudo npm install pm2@latest -g
```

Verify PM2 installation:

```bash
pm2 --version
```

## Application Deployment

### 3. Clone Source Code

Navigate to your deployment directory (e.g., `/root/`):

```bash
cd /root/
```

Clone both repositories:

```bash
# Clone token-ban-player repository
git clone https://github.com/dominicnguyen2601/token-ban-player.git token-ban-player-master

# Clone token-streaming-system repository
git clone https://github.com/dominicnguyen2601/token-streaming-system.git token-streaming-system-master
```

### 4. Deploy Token Ban Player

Run the deployment script for token-ban-player:

```bash
cd /root/token-ban-player-master
./deploy-token-ban-player
```

### 5. Deploy Token Streaming System

Run the deployment script for token-streaming-system:

```bash
cd /root/token-streaming-system-master
./deploy-token-streaming-system
```

### 6. Verify Deployment

Check that both applications are running:

```bash
pm2 list
```

You should see both `token-ban-player` and `token-streaming` in the process list with status "online".
