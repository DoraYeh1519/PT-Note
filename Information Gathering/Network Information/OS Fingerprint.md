利用各種作業系統版本對收到的封包所產生的不同回應封包內容，可用來區分辨識作業系統的類型或版本。

[[Nmap#^8a2dd1|Nmap]]就是利用此原理，以分辨不同版本的 UNIX
- Solaris
- HPUX
- AIX
- BSD
- Linux

還能夠辨識出不同版本的 Linux Kernel或其他作業系統，像是Windows

## 常見技術

- [[03_Penetration Testing Practice_網路資訊蒐集_v1.0.pdf#page=25&selection=8,0,9,2&color=yellow|TCP FIN flag偵測]]：檢測對未開 port 的回應方式
    
- [[03_Penetration Testing Practice_網路資訊蒐集_v1.0.pdf#page=25&selection=31,0,36,2&color=yellow|BOGUS flag偵測/偽造flag偵測]]：發送異常 TCP flag 封包觀察反應
    
- [[03_Penetration Testing Practice_網路資訊蒐集_v1.0.pdf#page=26&selection=8,0,8,16|TCP ISN Sampling]]：看初始序號變化
    
- [[03_Penetration Testing Practice_網路資訊蒐集_v1.0.pdf#page=26&selection=20,1,22,28|ICMP Error Message Quenching]]：比對錯誤訊息的速率與回應

