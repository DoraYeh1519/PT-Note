## DNS Zone Transfer 是什麼？

**DNS Zone Transfer（區域轉移）** 是 DNS 伺服器之間用來同步 DNS 記錄的一種機制，主要用於主從 DNS 之間的備援與更新。

## 核心概念

- 企業常自建多台 DNS 伺服器（主伺服器 + 備援伺服器）
- 為保持 DNS 資料一致，會啟用 Zone Transfer 功能
- 透過 `AXFR` 協定讓一台 DNS Server 取得另一台的完整 zone 記錄

## 安全風險

若未設定好存取限制，**外部人員也能要求 zone transfer**，導致以下資安問題：

1. **洩漏完整網域結構**（主機名稱、服務內容）
    
2. **揭露外網 IP 範圍**（便於攻擊者掃描）
    
3. **洩漏內部 IP 或測試主機資訊**
    
4. **大幅降低攻擊者偵查成本**


## 工具示範

使用 `dig` 或 [[nslookup]] 搭配 `axfr`：
```
dig axfr zonetransfer.me @nsztm1.digi.ninja
```

或在 Windows 下使用：
```
[[nslookup]]
server nsztm1.digi.ninja
ls -d zonetransfer.me
```

 線上工具：
- [https://hackertarget.com/zone-transfer/](https://hackertarget.com/zone-transfer/)    
- [https://tools.digitalpoint.com/zone-transfer](https://tools.digitalpoint.com/zone-transfer)

## 防護建議
在 DNS 設定檔（如 `/etc/named.conf`）中**限制允許 zone transfer 的 IP 清單**
```
options {
	allow-transfer { 1.2.3.4; 5.6.7.8; }; 
};
```