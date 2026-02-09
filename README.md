_These instructions are for those who already have a remote VPS._

## 1. Download [Bitvise_SSH_Client.exe](https://dl.bitvise.com/BvSshClient-Inst.exe):
- -> **"Login"** tab:
  - Host: *your vps ip
  - Port: 22
  - Username: root
  - Initial method: password (enter your password)
  - [x] "Store encrypted password in profile"  
- -> "**Services**" tab:
  - -> SOCKS / HTTP Proxy Forwarding :
    - [x] Enabled
    - Listen Interface: 127.0.0.1
    - Listen Port: 1080
- -> "**Options**" tab:
  - [ ] Open Terminal (off)
  - [ ] Open SFTP (off)
  - Reconnection: Always
- -> "**Log In**"

## 2. Download [Proxifier.exe](https://www.proxifier.com/download/ProxifierSetup.exe)

*activation

```
name: user
```


```
KFZUS-F3JGV-T95Y7-BXGAS-5NHHP
T3ZWQ-P2738-3FJWS-YE7HT-6NA3K
KFZUS-F3JGV-T95Y7-BXGAS-5NHHP
65Z2L-P36BY-YWJYC-TMJZL-YDZ2S
SFZHH-2Y246-Z483L-EU92B-LNYUA
GSZVS-5W4WA-T9F2E-L3XUX-68473
FTZ8A-R3CP8-AVHYW-KKRMQ-SYDLS
Q3ZWN-QWLZG-32G22-SCJXZ-9B5S4
DAZPH-G39D3-R4QY7-9PVAY-VQ6BU
KLZ5G-X37YY-65ZYN-EUSV7-WPPBS
6JZUY-32TKX-TK9W7-DU387-9RWKZ
L6Z8A-XY2J4-BTZ3P-ZZ7DF-A2Q9C（Portable Edition）
5EZ8G-C3WL5-B56YG-SCXM9-6QZAP（Standard Edition）<- Pick this one
P427L-9Y552-5433E-8DSR3-58Z68（MAC）
```
- -> "**Profile**":
  - -> **"Proxy Servers"**:
    - Add
    - Address: 127.0.0.1
    - Port: 1080
    - Protocol: SOCKS Version 5
    - Check:
      - *should be: `🟢Proxy is ready to work🟢` (be sure your Bitvise.exe's runnig correctly)
      - OK/Yes
- -> "**Profile**":
  - -> "**Proxification Rules**":
    - Add
    - Name: Bitvise
    - Applications
    - Browse (if the path is default)
  ```text
  C:\
  └── Program Files (x86)\
      └── Bitvise SSH Client\
          └── BvSsh.exe
  ```
  - Target Hosts: Any
  - Target Ports: Any
  - Action: Direct
  - Ok  

*! Important*: `The structure in Proxification Rules should be:`

| Rule Name | Applications | Target Hosts | Target Ports | Action |
| :--- | :--- | :--- | :--- | :--- |
| ☑️ **Localhost** | `Any` | `localhost; 127.0.0.1; %ComputerName%; ::1` | `Any` | `Direct` |
| ☑️ **Bitvise** | `bvssh.exe` | `Any` | `Any` | `Direct` |
| **Default** | `Any` | `Any` | `Any` | `Proxy SOCKS5 127.0.0.1` |

- -> "**Profile**":
  - -> "**Name Resolution**":
    - [ ] Select DNS names automatically (off)
    - [x] Resolve hostnames through proxy


## 3. Checking:
  - Open Bitvise
  - Hit "Logout" and then "Login"
  - Check your connection and geo on [2ip](https://2ip.ru) or [ip address lookup](https://iplocation.io/)
