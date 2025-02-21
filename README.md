# 🔒 OpenVPN Install Script – Fast, Secure, and Easy VPN Deployment

Easily set up a secure OpenVPN server on **Debian, Ubuntu, Fedora, CentOS, Arch Linux, Oracle Linux, Rocky Linux, and AlmaLinux** with this automated script.

---

## ✅ Key Features

✔ **Quick Installation** – Deploy a fully functional VPN in minutes.  
✔ **Enhanced Security** – Custom encryption settings for maximum protection.  
✔ **User Management** – Effortlessly add, remove, or manage clients.  
✔ **Multi-Platform Support** – Works on various Linux distributions.  
✔ **Automated Headless Installation** – One-command setup for seamless deployment.  

---

## 🖥️ Supported Distributions

| Distribution        | Support        |
| ------------------- | -------------- |
| AlmaLinux 8         | ✅             |
| Amazon Linux 2      | ✅             |
| Arch Linux          | ✅             |
| CentOS 7            | ✅ 🤖          |
| CentOS Stream >= 8  | ✅ 🤖          |
| Debian >= 10        | ✅ 🤖          |
| Fedora >= 35        | ✅ 🤖          |
| Oracle Linux 8      | ✅             |
| Rocky Linux 8       | ✅             |
| Ubuntu >= 18.04     | ✅ 🤖          |

*Note: Distributions marked with 🤖 are regularly tested.*

---

## 📥 Installation Guide

### Step 1: Download the Script

```bash
curl -O https://raw.githubusercontent.com/InfernoVM/OpenVPN-Installer/main/setup.sh
chmod +x setup.sh
```

### Step 2: Run the Script

```bash
sudo ./setup.sh
```

Follow the prompts to configure your VPN server.

### Step 3: Manage Clients

Once installed, rerun the script to:

- **Add a Client**
- **Remove a Client**
- **Uninstall OpenVPN**

Client configuration files (`.ovpn`) will be saved in your home directory for easy access.

---

## 🔄 Automated Headless Installation

To automate the installation:

```bash
AUTO_INSTALL=y ./setup.sh
```

Or set environment variables:

```bash
export AUTO_INSTALL=y
./setup.sh
```

### Customizable Options

- `APPROVE_INSTALL=y`  
- `APPROVE_IP=y`  
- `IPV6_SUPPORT=n`  
- `PORT_CHOICE=1`  
- `PROTOCOL_CHOICE=1`  
- `DNS=1`  
- `COMPRESSION_ENABLED=n`  
- `CUSTOMIZE_ENC=n`  
- `CLIENT=clientname`  
- `PASS=1`  

To set the server endpoint behind NAT:

```bash
ENDPOINT=$(curl -4 ifconfig.co)
```

For more customization, modify the `installQuestions()` function in the script.

### 📌 Headless User Addition

To automate user creation:

```bash
#!/bin/bash
export MENU_OPTION="1"
export CLIENT="foo"
export PASS="1"
./setup.sh
```

---

## 🔐 Advanced Security and Encryption

OpenVPN defaults to **strong encryption settings**, further enhanced by this script:

- **AES-GCM** – Ensures confidentiality, integrity, and authenticity.  
- **TLS 1.2** – Enforced for maximum security.  
- **ECDSA Certificates** – Default certificate type for efficiency and security.  
- **tls-crypt** – Enabled by default for additional privacy and DoS protection.  

---

## 🤔 FAQ

### 🔹 Recommended VPS Providers
- **[InfernoVM](https://infernovm.net)**

### 🔹 Recommended OpenVPN Clients

- **Windows** – [Official OpenVPN Community Client](https://openvpn.net/index.php/download/community-downloads.html)  
- **Linux** – Install `openvpn` via your distribution’s package manager ([APT repo](https://community.openvpn.net/openvpn/wiki/OpenvpnSoftwareRepos))  
- **macOS** – [Tunnelblick](https://tunnelblick.net/), [Viscosity](https://www.sparklabs.com/viscosity/)  
- **Android** – [OpenVPN for Android](https://play.google.com/store/apps/details?id=de.blinkt.openvpn)  
- **iOS** – [OpenVPN Connect](https://itunes.apple.com/us/app/openvpn-connect/id590379981)

### 🔹 Is This Script NSA-Proof?

No. While it enhances security, **no VPN can guarantee complete anonymity**. Evaluate your threat model accordingly.

### 🔹 Where Can I Find OpenVPN Documentation?

Check the [OpenVPN Manual](https://community.openvpn.net/openvpn/wiki/Openvpn24ManPage) for full documentation.

---

## 🔧 Security and Encryption Details

> **Warning**: This section has not been updated for OpenVPN 2.5+.

### 📌 Compression
- **Default** – Compression is disabled to prevent VORACLE attacks.  
- **Supported** – LZ0 and LZ4 (v1/v2) are available but not recommended.  

### 📌 TLS Version
- **Default** – TLS 1.2 enforced (`tls-version-min 1.2`).  
- **Support** – Available since OpenVPN 2.3.3.  

### 📌 Certificates
- **Default** – ECDSA with `prime256v1` curve.  
- **Supported** – RSA keys (2048, 3072, 4096 bits) and ECDSA curves (`secp384r1`, `secp521r1`).  

### 📌 Data Channel Encryption
- **Default** – AES-128-GCM.  
- **Supported** – AES-GCM and AES-CBC with multiple key lengths.  

### 📌 Control Channel Encryption
- **Default** – `TLS-ECDHE-*` with AES-128-GCM and SHA256.  
- **Supported** – Configurable based on certificate type (ECDSA or RSA).  

### 📌 Diffie-Hellman Key Exchange
- **Default** – ECDH with `prime256v1`.  
- **Supported** – ECDH and classic DH keys.  

### 📌 HMAC Digest Algorithm
- **Default** – SHA256.  
- **Supported** – SHA256, SHA384, SHA512.  

### 📌 `tls-auth` and `tls-crypt`
- **Default** – `tls-crypt` enabled for additional security.  
- **Supported** – Both `tls-auth` and `tls-crypt`.  

---

📌 **Why Use This Script?**
✔ **Fast & Secure** – Minimal setup, maximum security.  
✔ **Customizable** – Adjust settings for your needs.  
✔ **Lightweight & Efficient** – No unnecessary bloat.

➡️ **Download and deploy your VPN today!** 🚀

