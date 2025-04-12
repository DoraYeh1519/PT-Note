WHOIS (whois)是用來查詢網際網路中域名的IP以及所有者等資訊的傳輸協定。

現在出現了一些基於網頁介面的簡化線上查詢工具，甚至可以 一次向不同的資料庫查詢。

網頁介面的查詢工具仍然依賴WHOIS協定向伺服器傳送查詢 請求，command line下的whois工具仍然被系統管理員廣泛使用。

## Usage

`whois [options] [IP]`

- -h host ：指定網域名稱解析伺服器，預設透過 whois.networksolutions.com或是whois.arin.net來進行解析。 

- -p POST ：預設為43，可以透過指令指定要連接的port