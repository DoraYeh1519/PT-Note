### 📌 工具簡介

- **用途**：密碼破解（主要針對雜湊值，離線破解）
- **開源工具**，支援多種雜湊格式與密碼存儲類型
- 可搭配字典攻擊、暴力破解、規則變形等策略
    

### 🧠 功能特色

- 支援常見密碼雜湊格式：
    - `/etc/shadow`、`htpasswd`、zip、rar、PDF、Office 文件、Wi-Fi Handshake

- 攻擊模式：
    
    - **字典攻擊**（wordlist）
    - **Incremental（暴力破解）**
    - **Rules（變形規則）**
        
- 能自動偵測 hash 格式
- 支援自訂 cracking rule（強大但略具學習曲線）

### 指令介紹
[[05_Penetration Testing Practice_系統通行碼_v1.0.pdf#page=66&selection=2,0,10,10&color=yellow|常用指令對照]]

```
# 基本字典破解 john 
--wordlist=rockyou.txt hashes.txt  

# 指定 hash 類型 
john --format=raw-md5 hashes.txt  

# 查看破解進度 
john --status  

# 顯示已破解密碼 
john --show hashes.txt
```