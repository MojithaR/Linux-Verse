# Networking Basics 🌐

## Basic Network Commands 🖧

| Command      | Description                                      |
|--------------|--------------------------------------------------|
| `ifconfig`   | Displays or configures network interface details. |
| `ping`       | Tests connectivity to a remote host.              |
| `netstat`    | Displays network connections, routing tables, etc.|

## Configuring Network Interfaces 🛠️

- **Network Configuration**: Configure IP addresses, routes, and DNS settings using files like `/etc/network/interfaces` or tools like `nmcli` or `ip`.

## SSH and Remote Access 🔑

- **SSH (Secure Shell)**: Provides secure command-line access to remote systems.
  - Example: `ssh username@hostname`

- **Remote Access**: Tools like `ssh`, `scp` (secure copy), and `sftp` (secure file transfer protocol) facilitate remote management and file transfer securely.

## Network Troubleshooting 🛠️

| Command        | Description                                      |
|----------------|--------------------------------------------------|
| `traceroute`   | Traces the route packets take to a network host.  |
| `nslookup`     | Queries DNS servers for domain name resolution.   |

### Examples
```bash
# Display network interfaces
ifconfig

# Ping a remote host
ping example.com

# Display network connections and routing tables
netstat -rn

# Trace the route to a network host
traceroute example.com

# Perform DNS lookup
nslookup example.com

### Summary
Networking basics in Linux involve understanding essential commands like ifconfig, ping, and netstat for network interface management, connectivity testing, and network status. Configuring network interfaces involves setting IP addresses, routes, and DNS. SSH provides secure remote access, while tools like traceroute and nslookup aid in troubleshooting network issues by tracing routes and querying DNS servers, respectively.
