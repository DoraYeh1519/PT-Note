[[05_Penetration Testing Practice_系統通行碼_v1.0.pdf#page=59&selection=2,0,3,15&color=yellow|05_Penetration Testing Practice_系統通行碼_v1.0, p.59]]
### 📌 IPFS 是什麼？

- **IPFS（InterPlanetary File System）** 是一種去中心化的檔案儲存與分發協議，檔案以**內容位址（CID）** 方式存取，而非依照 URL/網域。

- 特性：
    - 分散式、抗審查、無法輕易下架
    - CID 一旦生成就幾乎**永久有效**
    - 無法輕易透過封鎖網域或移除主機來終止存取

### 🚨 威脅趨勢概述

1. **傳統釣魚網站被移除速度快，攻擊者轉向 IPFS**
    - 過往釣魚連結多放在雲端平台（如 Google Drive、Dropbox），一旦被舉報就會被下架
    - IPFS 協議無單點控制，極難移除
        
2. **IPFS 被用來存放釣魚頁面或惡意檔案**
    - 包含仿冒登入頁、假帳單、木馬壓縮檔等
    - CID 永久指向相同內容，讓詐騙連結「難以拔除」
        
3. **攻擊郵件中的連結樣式改變**
    - 使用「瀏覽器 IPFS 網關」例如：   
            ```https://cloudflare-ipfs.com/ipfs/{CID}
            https://ipfs.io/ipfs/{CID}```
    - 表面上是 HTTPS 連結，實際上導向的是不可控的 IPFS 內容

### 真實案例分析（簡述）

#### 📧 案例一：IPFS 銀行釣魚頁
- 主旨：冒充銀行通知帳號異常
- 內文附上 IPFS 連結，聲稱需重新登入以驗證帳戶
- 點入後出現仿真登入頁面（實為 IPFS 上的靜態頁面）
- 受害者輸入帳號密碼後直接送至攻擊者伺服器

#### 📧 案例二：IPFS 存放惡意壓縮檔
- 郵件內嵌 IPFS 連結，檔名偽裝為合約、發票、出貨單
- 實際內容為 .zip 壓縮檔，內含 RAT（遠端遙控木馬）
- 傳統安全閘道因無法即時解析 CID，難以判斷風險

### 🛡️ 防禦與監控建議

1. **郵件過濾器新增 IPFS Gateway 偵測**
    
    - 常見 gateway：
        - `cloudflare-ipfs.com`
        - `ipfs.io`
        - `gateway.pinata.cloud`
    - 可將 IPFS URL 加入監控條件
        
2. **教育使用者避免點擊陌生連結**
    
    - 對 CID 開頭的不明 URL 提高警覺
    - 不下載來路不明的壓縮檔或文件
        
3. **安全閘道加強內容層解析**
    
    - 對郵件內嵌的網址執行行為沙箱分析
    - 若內容指向 IPFS，進一步模擬點擊結果
        
4. **使用 IPFS 分流分析平台**
    
    - 部分資安廠商如 [[OSINT Tool#^ecfcee|VirusTotal]]、ANY.RUN 已支援對 IPFS CID 的分析