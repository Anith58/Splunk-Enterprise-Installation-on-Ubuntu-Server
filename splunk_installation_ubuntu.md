# 🧠 Splunk Enterprise Installation on Ubuntu Server

This guide explains how to install Splunk Enterprise on an Ubuntu Server (20.04/22.04) with step-by-step commands and explanations.

---

## 💾 System Requirements

- Ubuntu Server 20.04 / 22.04 (64-bit)
- Minimum 2 GB RAM (Recommended: 4 GB+)
- 5 GB+ Disk space

---

## 🗜️ Step 1: Download Splunk Enterprise

Go to [Splunk Downloads](https://www.splunk.com/en_us/download/splunk-enterprise.html) and download the `.deb` installer for Linux.

Or, use `wget` to download directly:

```bash
wget -O splunk-9.2.1-ae6821b2b081-Linux-x86_64.deb "https://download.splunk.com/products/splunk/releases/9.2.1/linux/splunk-9.2.1-ae6821b2b081-Linux-x86_64.deb"
```

> 📌 Replace the version with the latest one from the Splunk site.

---

## 📦 Step 2: Install the .deb package

```bash
sudo dpkg -i splunk-9.2.1-ae6821b2b081-Linux-x86_64.deb
```

This command installs the Splunk binaries under `/opt/splunk`.

---

## 🧑‍💻 Step 3: Accept License and Start Splunk

Run this command to start Splunk and accept the license agreement:

```bash
sudo /opt/splunk/bin/splunk start --accept-license
```

You'll be prompted to set up an admin **username** and **password**.

---

## 🔁 Step 4: Enable Splunk to Start at Boot

To enable Splunk as a boot-time service:

```bash
sudo /opt/splunk/bin/splunk enable boot-start
```

---

## 🌐 Step 5: Access Splunk Web

Once running, open your browser and go to:

```
http://<your-server-ip>:8000
```

> Log in using the admin credentials you set earlier.

---

## 🛠️ Useful Splunk Commands

| Action            | Command                                         |
| ----------------- | ----------------------------------------------- |
| Start Splunk      | `sudo /opt/splunk/bin/splunk start`             |
| Stop Splunk       | `sudo /opt/splunk/bin/splunk stop`              |
| Restart Splunk    | `sudo /opt/splunk/bin/splunk restart`           |
| Check status      | `sudo /opt/splunk/bin/splunk status`            |
| Enable auto-start | `sudo /opt/splunk/bin/splunk enable boot-start` |

> ✅ To check Splunk service status:
>
> ```bash
> sudo /opt/splunk/bin/splunk status
> ```
>
> This shows whether the Splunk service is running, stopping, or stopped.

---

## ✅ Post-Installation Tips

- Add firewall rules if using `ufw`:
  ```bash
  sudo ufw allow 8000/tcp
  ```
- Ensure the server has enough disk space using `df -h`.
- Monitor logs: `/opt/splunk/var/log/splunk/`

---

## 📌 References

- [Splunk Official Docs](https://docs.splunk.com/)
- [Splunk Admin Manual](https://docs.splunk.com/Documentation/Splunk/latest/Admin)

---

## ✍️ Author

Created by [ANITH]

