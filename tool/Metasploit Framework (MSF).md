- 最主流的弱點利用平台，由 Rapid7 維護，支援 Windows/Linux/macOS
- 包含大量 exploit、payload、掃描工具
- CLI 工具為 `msfconsole`，GUI 工具有 Armitage、Web UI

## 🔧 主要元件 ＆ 架構

| 元件              | 說明                    |
| --------------- | --------------------- |
| **exploit**     | 攻擊程式，針對特定漏洞           |
| **payload**     | 攻擊成功後執行程式（如反向 shell）  |
| **shellcode**   | 編碼的 payload 指令        |
| **listener**    | 攻擊端監聽連線               |
| **module**      | 弱點模組、輔助模組等            |
| **meterpreter** | 高互動性 payload，可完全操控受害端 |
![[07_Penetration Testing Practice_弱點利用平台_v1.0.pdf#page=23&rect=154,33,809,461|07_Penetration Testing Practice_弱點利用平台_v1.0, p.23]]
## 🧪 常見操作指令

```
# 啟動
Metasploit msfconsole

# 搜尋模組
search exploit samba

# 載入模組
use exploit/linux/samba/...

# 參考模組設定
show options

# 設定參數
set <options> <value>
// set RHOSTS <目標IP> 
// set PAYLOAD <payload類型> 
// set LHOST <攻擊者IP>  

# 執行攻擊
exploit
```