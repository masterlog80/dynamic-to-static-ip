# Dynamic to Static IP – Ubuntu Server 24.04

A Bash script that simplifies converting a dynamic IP address to a static IP configuration on Ubuntu Server 24.04. It walks you through every step interactively and is designed to be accessible to users with limited networking experience.

---

## Features

- **Welcome & overview** – Greets the user and explains what the script will do before making any changes
- **User authentication** – Displays the current user and requests explicit confirmation to proceed
- **Network interface detection** – Automatically identifies the active network interface (ensure only one cable is plugged in)
- **Current settings display** – Shows existing IP address, netmask, gateway, and DHCP4/DHCP6 status
- **Guided input prompts** – Prompts for new static IP, netmask, gateway, DNS servers, and hostname
- **Netplan config management** – Locates the existing Netplan file, creates a timestamped backup, and writes a new configuration
- **Safe apply with rollback** – Asks for confirmation before applying; if declined, automatically reverts to the original configuration

---

## Quick Start

### Requirements

- Ubuntu Server 24.04
- Bash
- Root / sudo access

### Clone & run

```bash
git clone https://github.com/masterlog80/dynamic-to-static-ip.git
cd dynamic-to-static-ip
sudo chmod +x static-ip.sh
sudo ./static-ip.sh
```

### Uninstall / rollback

The script creates a backup of your original Netplan configuration before making any changes. To restore it manually:

```bash
# The backup is saved alongside the original, e.g.:
sudo cp /etc/netplan/00-installer-config.yaml.bak /etc/netplan/00-installer-config.yaml
sudo netplan apply
```

---

## Usage

1. **Run the script** as root on your Ubuntu Server 24.04 machine.
2. **Confirm** the active network interface detected by the script.
3. **Enter** your desired static IP, subnet mask, gateway, DNS server(s), and hostname when prompted.
4. **Review** the summary and confirm to apply, or decline to revert all changes automatically.

---

## Screenshots

<img width="587" alt="Dynamic to Static IP script terminal output" src="https://github.com/user-attachments/assets/3f495c6f-d10e-42d1-97f5-ca62f4685bd2">

---

## License

[MIT](LICENSE)
