-  hping/hping3 是一個網路工具，可以用來測試firewall、網路效能、觀察遠端主機的回應狀態，包括
	- TCP
	- UDP
	- ICMP

## 功能

- 判斷是否有防火牆保護 
- port掃描 
- 辨別網路協定、作業系統類型、port服務類型 
- 估算路徑上的最大傳輸量 
- 壓力測試 
- 可以由使用者自訂封包格式和偽造IP

## Usage
![[03_Penetration Testing Practice_網路資訊蒐集_v1.0.pdf#page=21]]

- 常用參數：
    
    - `-S`：SYN 掃描
        
    - `-p`：指定 port
        
    - `-i u100`：每 100 微秒發送一包（flooding）