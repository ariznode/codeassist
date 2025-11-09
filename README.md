# How to run Codeassist using Ubuntu WSL

## Reruitmens
Minimum Specification

Make sure to be root user on your wsl/ubuntu

```bash
sudo su
```

CPU : 4 core
RAM : 8GB

This guide working for local pc Ubuntu/WSL, and not working for VPS!

# Installation

#### Install Dependencies

```bash
apt update && apt upgrade -y
```

```bash
apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev -y
```

## Docker
```bash
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test Docker
sudo docker run hello-world

```

## Python

```bash
apt install python3 python3-pip python3-venv python3-dev -y
```

## UV

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
export PATH="/root/.local/bin:$PATH"
```

Verify UV instalation
```bash
uv --version
```

# Clone Codeassist Repository

```bash
git clone https://github.com/gensyn-ai/codeassist.git
cd codeassist
```

# Running

To run CodeAssist, simply execute the following command:

```bash
uv run run.py
```
<img src="https://drive.google.com/uc?export=view&id=1dETs3b1fw2rpHzW_qSOZ8_1fkY-BArrT" width="600">

If you see this, wait a minut then enter your hugging face token

## HuggingFace Token

To start CodeAssist, you will need to have a HuggingFace token. Follow [these instructions](https://huggingface.co/docs/hub/en/security-tokens) and generate a token with `Write` access.

# Login

After you see http://localhost:3000 on terminal open http://localhost:3000 then login, after login complete mission

Note if you are running swarm you can change port 3000 to 3001 on 
```bash
nano run.py
```




