- 語法：nslookup [Option] HOST [Server] 
- 選項：
	- `HOST`: 查詢目標的hostname
	- `Server`:指定要向哪台DNS伺服器查詢，如果沒有輸入則會以本地端設定的 DNS 伺服器查詢
	- `-debug`: 是否顯示查詢過程中的封包資訊 
	- `-d2`: 更詳細的顯示執行過程中的封包回應資訊 
	- `--port=VALUE`: 預設port為53 ，如不是預設port，可以利用port來指定
	- `-type=VALUE`: 指定查詢的資源類型，預設是A(IPv4) 


VALUE值：

> [!NOTE]
>  ![[DNS RR type]]


