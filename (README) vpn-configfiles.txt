# =========================================================
# VPN Configuration File
# Project: HomeVPN-2
# Description: Secondary VPN server and certificate setup
# Created on: (add your date)
# =========================================================

[Server]
# Local/private IP address of the VPN server
IP = 192.168.1.20

# Port used for VPN connections
Port = 443

# Supported protocols: SSTP / L2TP / IKEv2 / OpenVPN
Protocol = SSTP

# Encryption method
Encryption = AES128-CBC

# Authentication method: Certificate / Password / Mixed
AuthMethod = Certificate

# Certificate paths (replace later with your real ones)
RootCert = certs/rootCA2.crt
ServerCert = certs/vpnserver2.crt
PrivateKey = certs/vpnserver2.key

# Whether to allow external clients (set true once tested)
AllowExternalConnections = false


[Client]
# Public IP or domain of the VPN server
ServerAddress = examplevpn2.ddns.net

# User login (for password-based VPNs; skip if cert-only)
Username = vpnuser2
Password = (to be set)

# Use certificate authentication
UseCertificate = true
ClientCert = certs/client2.crt
ClientKey = certs/client2.key


[Network]
# IP range assigned to VPN clients
AssignIPRange = 10.20.0.1-10.20.0.50

# DNS servers pushed to clients
DNS1 = 8.8.8.8
DNS2 = 1.1.1.1

# Routes (optional)
Route1 = 0.0.0.0/0
Route2 = 192.168.1.0/24


[Advanced]
# Log settings
EnableLogging = true
LogPath = logs/vpnserver2.log

# Max connections
MaxClients = 10

# Auto restart server if connection drops
AutoRestart = true
