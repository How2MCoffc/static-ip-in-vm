# Setting Up a Static IP Address in Ubuntu Using Netplan

## Introduction

This guide will walk you through the process of setting up a static IP address on your Ubuntu system using Netplan. Follow the steps below to configure your network settings.

### Step 1: Open the Netplan Configuration File

Open the Netplan configuration file using a text editor (e.g., nano):

```bash
sudo nano /etc/netplan/01-netcfg.yaml
```

### Step 2: Modify the Configuration File
```
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:  # Replace with your actual network interface name
      dhcp4: no
      addresses: [<static_ip>/24]
      gateway4: <gateway_ip>
      nameservers:
        addresses: [<dns_server_ip1>, <dns_server_ip2>]
```
### Step 3: Save and Apply the Configuration
```
sudo netplan apply
```
### Step 4: Restart the Network Service
```
sudo systemctl restart systemd-networkd
```
Now, your Ubuntu system is configured with a static IP address. Ensure the accuracy of the provided information and adapt the configuration to your specific network setup.
