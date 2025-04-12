> [!PDF|note] [[03_Penetration Testing Practice_網路資訊蒐集_v1.0.pdf#page=27&selection=6,0,36,11&color=note|03_Penetration Testing Practice_網路資訊蒐集_v1.0, p.27]]
> > 若靠著前面部分所提到的資料收集以及非惡意性的掃描，都沒辦法取得有用的資訊時，可嘗試利用目標系統的有效資源共享以及使用者帳號，利用 Enumeration (列舉) 來達到取得有效用的資訊，以便尋找漏洞進行進一步的滲透行為
> > 
> > 常用的列舉工具包括DNS相關列舉
> > 
> > 在Windows作業系統中，Netbios相關漏洞常令滲透者建立連線之後，再透過不同的列舉技術來取得資訊，常列舉的資訊項目包含了網路資源與共享、使用者名稱與群組名稱、應用程式等

## 工具
- DNS 列舉
	- dig
	- [[nslookup]]
	- [[DNSenum]]
- SNMP
	- [[snmpwalk]]