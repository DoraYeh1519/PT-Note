### 🛡️ 防毒 / 防火牆繞過

- 關閉 Defender 功能（PowerShell）
- 加入白名單目錄/程序（`Set-MpPreference`）
- 關閉防火牆（`netsh advfirewall`）

### 🧬 UAC 繞過

- 利用不需提示的系統行為觸發高權限程式
    
- 範例：`sdclt.exe` 配合 `kickoffelev` + `Registry` 控制攻擊流程
    
    - Registry 路徑：
        
        `HKCU\Software\Classes\exefile\shell\runas\command\IsolatedCommand`