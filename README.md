# WSL Ubuntu Setup Guide

A step-by-step guide to installing Windows Subsystem for Linux (WSL) and Ubuntu on Windows, including installation commands, configuration, verification, useful WSL commands, and troubleshooting tips.

## 1. Install WSL on Windows

Open **Windows PowerShell as Administrator** or **Windows Terminal as Administrator**.

### Recommended: Install WSL with Ubuntu

```powershell
wsl --install
```

This installs WSL and the default Ubuntu distribution. Restart Windows if prompted.

### Install Ubuntu explicitly

```powershell
wsl --install -d Ubuntu
```

### List available Linux distributions

```powershell
wsl --list --online
```

### Install a specific Ubuntu LTS version

```powershell
wsl --install -d Ubuntu-24.04
```

**Note:** Choose the appropriate installation command. If Ubuntu is already installed, check its status before attempting to install it again.

## 2. Check WSL Installation and Status

Run these commands in PowerShell:

| Command | Purpose |
|---|---|
| `wsl --status` | Check WSL configuration |
| `wsl --version` | Check WSL component versions |
| `wsl --list --verbose` | List installed distributions and their WSL versions |
| `wsl --list --online` | List available distributions |
| `wsl --help` | Display available WSL commands |

## 3. Start and Manage Ubuntu

Run these commands in PowerShell:

```powershell
# Launch the default Linux distribution
wsl

# Launch Ubuntu explicitly
wsl -d Ubuntu

# Stop all running WSL distributions
wsl --shutdown

# Stop only Ubuntu
wsl --terminate Ubuntu

# Set WSL 2 as the default for new installations
wsl --set-default-version 2

# Set Ubuntu to use WSL 2
wsl --set-version Ubuntu 2
```

**Note:** If you installed a specific Ubuntu version, replace `Ubuntu` with its exact distribution name, such as `Ubuntu-24.04`.

## 4. Update Ubuntu Packages

Open the Ubuntu terminal and run:

```bash
# Refresh the package list
sudo apt update

# Upgrade installed packages
sudo apt upgrade -y

# Remove unnecessary packages
sudo apt autoremove -y

# Check Ubuntu version
lsb_release -a

# Check Linux kernel version
uname -r
```

## 5. Troubleshooting WSL

If WSL hangs, fails to launch, or encounters a timeout, open PowerShell as Administrator.

```powershell
# Shut down WSL
wsl --shutdown

# Update WSL
wsl --update

# Check installed distributions
wsl --list --verbose

# Launch Ubuntu
wsl -d Ubuntu
```

If the issue persists, save your work and restart Windows:

```powershell
Restart-Computer
```

**Important:** A timeout does not necessarily mean Ubuntu failed to install. Check the installed distributions before attempting another installation.

## 6. Complete Installation Workflow

Follow these steps in order.

### Step 1 — Install WSL (PowerShell as Administrator)

```powershell
wsl --install
```

Restart Windows if prompted.

### Step 2 — Launch Ubuntu

```powershell
wsl -d Ubuntu
```

Create your Linux username and password when prompted during the initial setup.

### Step 3 — Update Ubuntu (Ubuntu terminal)

```bash
sudo apt update
sudo apt upgrade -y
```

### Step 4 — Verify the installation (PowerShell)

```powershell
wsl --list --verbose
```

Confirm that Ubuntu appears in the list and uses **WSL 2**.

## Official References

- [Microsoft Learn — Install WSL](https://learn.microsoft.com/en-us/windows/wsl/install)
- [Microsoft Learn — Basic WSL Commands](https://learn.microsoft.com/en-us/windows/wsl/basic-commands)
