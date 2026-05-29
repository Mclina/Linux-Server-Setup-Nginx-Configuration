
This repository contains the configuration and documentation for the HNG12 Stage 0 DevOps task. The goal was to deploy a secure Linux server, configure a web server (Nginx), and expose a public API endpoint over HTTPS.

## 🚀 Project Overview

- **Domain:** [https://mariacelin.duckdns.org/api](https://mariacelin.duckdns.org/api)
- **Infrastructure:** AWS EC2 (Ubuntu 24.04 LTS)
- **Web Server:** Nginx
- **Security:** UFW Firewall, SSH Hardening, Let's Encrypt SSL

## 🛠️ Implementation Details

### 1. Server Hardening (SSH)
- Disabled root login to prevent brute-force attacks.
- Disabled password authentication; access is strictly via SSH Key pairs.
- Configured a non-root user with sudo privileges.

### 2. Firewall Configuration (UFW)
The firewall is active and strictly limited to the following ports:
- **22/TCP**: Secure Shell (SSH)
- **80/TCP**: HTTP (Redirected to HTTPS)
- **443/TCP**: HTTPS (SSL/TLS)

### 3. Nginx & API Setup
Nginx is configured to serve a JSON response at the `/api` endpoint.
- **Endpoint:** `/api`
- **Response Format:**
  ```json
  {
    "message": "HNGI14 Stage 0",
    "track": "DevOps",
    "username": "mariacelin"
  }
4. SSL/TLS Encryption
The site is secured using Certbot and Let's Encrypt.

Automated HTTP to HTTPS redirection is enabled.

SSL certificates are set to auto-renew.

🧪 Testing the API
You can verify the deployment by running the following command in your terminal:

Bash
curl -i [https://mariacelin.duckdns.org/api](https://mariacelin.duckdns.org/api
