**The repository `O11-OTT-V2.2b1` is a patched build of the O11 OTT streamer, designed to be free and accessible for everyone. It’s a public fork of [DRMStuff/o11-OTT-v2.2b1](https://github.com/DRMStuff/o11-OTT-v2.2b1)**  ![Badge](https://hitscounter.dev/api/hit?url=https%3A%2F%2Fgithub.com%2Fsohag1192%2FO11-OTT-V2.2b1&label=Visitors&icon=github&color=%23198754&message=&style=for-the-badge&tz=UTC)

---

### 📖 Project Overview
- **Name:** O11 OTT v2.2b1  
- **Purpose:** Patched version of the O11 OTT streamer, removing restrictions and making it freely usable.  
- **Main File:** `o11_v22b1-DRMStuff` (likely the executable or launcher).  
- **Status:** Public fork maintained under your GitHub account.  



---

### ⚙️ Installation Instructions (ইনস্টলেশন নির্দেশাবলী)

#### 1. Clone the Repository
```bash
git clone https://github.com/sohag1192/O11-OTT-V2.2b1.git
cd O11-OTT-V2.2b1
```

#### 2. Make the Binary Executable
```bash
chmod +x o11_v22b1-DRMStuff
```

#### 3. Run Manually
```bash
./o11_v22b1-DRMStuff
```

👉 **Bangla Note:**  
```markdown
রিপোজিটরি ক্লোন করার পর `o11_v22b1-DRMStuff` ফাইলটিকে executable করতে হবে। তারপর সরাসরি চালাতে পারবেন।
```

---

### 🔄 Auto‑Start on Boot (স্বয়ংক্রিয়ভাবে চালু)


### ✅ Steps to Enable Auto‑Start on Boot
1. **Create a systemd service file**  
   ```bash
   sudo nano /etc/systemd/system/o11ott.service
   ```
   
2. **Add the following content** (adjust paths if needed):
   ```ini
   [Unit]
   Description=O11 OTT V2.2b1 DRMStuff Service
   After=network.target

   [Service]
   Type=simple
   WorkingDirectory=/root/O11-OTT-V2.2b1
   ExecStart=/root/O11-OTT-V2.2b1/o11_v22b1-DRMStuff
   Restart=always
   RestartSec=5

   [Install]
   WantedBy=multi-user.target
   ```

   - `WorkingDirectory` points to the folder where your binary lives.  
   - `ExecStart` is the command you currently run manually.  
   - `Restart=always` ensures it comes back if it crashes.  

3. **Reload systemd and enable the service**  
   ```bash
   sudo systemctl daemon-reload
   sudo systemctl enable o11ott.service
   sudo systemctl start o11ott.service
   ```

4. **Check status**  
   ```bash
   systemctl status o11ott.service
   ```

### 🔄 Alternative (quick & dirty)
If you don’t want to use systemd, you could add the command to `/etc/rc.local` or a cron job with `@reboot`, but systemd is far more reliable and gives you logging + restart control.

---



👉 **Bangla Note:**  
```markdown
উপরের systemd ফাইলটি তৈরি করে enable করলে সার্ভার রিবুটের পর স্বয়ংক্রিয়ভাবে স্ট্রিমার চালু হবে।
```

---

### 📋 Logs & Monitoring
```bash
journalctl -u o11ott.service -f
```

👉 **Bangla Note:**  
```markdown
লগ দেখতে `journalctl` কমান্ড ব্যবহার করুন।
```

---

### 🗑️ Uninstall
```bash
sudo systemctl disable o11ott.service
sudo rm /etc/systemd/system/o11ott.service
```

👉 **Bangla Note:**  
```markdown
সার্ভিস বন্ধ করতে এবং মুছে ফেলতে উপরের কমান্ডগুলো ব্যবহার করুন।
```

---

---

## 🙋 Contributing

- Issues and pull requests are welcome.  
- If you find bugs or want to suggest improvements, please open an issue or PR.  

📬 **Contact via Mail:** [sohag1192@gmail.com](mailto:sohag1192@gmail.com)

📬 **Contact via Telegram:** [Md_Sohag_Rana](https://t.me/Md_Sohag_Rana)

---

## 🌟 Support

If you enjoy this project, please ⭐ it on GitHub — your support motivates future updates!



