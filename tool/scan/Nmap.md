Nmap全名是**Network Mapper**，是由Gordon Lyon (aka his pseudonym: Fyodor Vaskovich)所開發的一套開放原始碼軟體。 

可用於檢測本機或網路遠端主機的安全性弱點

主要功能是針對來源主機/網段作掃描：
- 目標主機所開放的TCP埠
- 取得對應的網路服務類型 
- 應用軟體名稱與版本 

也可偵測出目標主機所使用的
- 作業系統
- 封包過濾器
- 防火牆種類等資訊

若要在windows下使用時，可利用圖形介面的Zenmap

## Usage

- [[ASN]] Scan
```
nmap --script asn-query IP
```

- [[掃描技術#^30b0c4|TCP 全連接掃描]] ^229480
```
nmap –sT IP
```

- [[掃描技術#^30b0c4|TCP 半連接掃描]] ^e6b92e
```
nmap –sS IP
```

- [[掃描技術#^30b0c4|UDP掃描]] ^211e4f
```
nmap –sU IP
```

- [[掃描技術#^e846d5|Port及對應服務掃描]] ^d26436
```
nmap -sV IP
```

- [[掃描技術#^07057f|作業系統掃描]] ^8a2dd1
```
nmap -O IP
```