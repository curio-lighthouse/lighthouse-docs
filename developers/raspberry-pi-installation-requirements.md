---
description: Required software for the Raspberry Pi
---

# Raspberry Pi Installation Requirements

## Settings

### Enable serial communication

```bash
sudo nano /boot/config.txt
```

Add the line below at the end of the config.txt file.

```bash
enable_uart=1
```

### Enable Bluetooth discovery

```bash
sudo hciconfig hci0 piscan
```

## Installing Required Tooling

Update your system.

```
sudo apt update
```

### Install Bluez

```
sudo apt-get install bluetooth bluez libbluetooth-dev
sudo python3 -m pip install pybluez
```



