<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,45:0f3d2e,100:00ff9c&height=250&section=header&text=b4x0rn&fontSize=84&fontColor=ffffff&fontAlignY=36&stroke=00ff9c&strokeWidth=1&desc=OFFENSIVE%20SECURITY%20%C2%B7%20ACTIVE%20DIRECTORY%20%C2%B7%20RED%20TEAM&descSize=17&descAlignY=58&animation=fadeIn" width="100%"/>

<a href="https://x0ph3nt.com">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&pause=1100&color=00FF9C&center=true&vCenter=true&width=700&height=40&lines=%24+Enumerate.+Exploit.+Escalate.+Document.;%24+Active+Directory+attack+paths+%7C+Web+%7C+Linux;%24+Roadmap%3A+CRTP+%E2%86%92+OSCP;%24+Always+improving.+Always+learning." alt="typing"/>
</a>

<br/><br/>

<a href="https://x0ph3nt.com"><img src="https://img.shields.io/badge/WRITEUPS-x0ph3nt.com-00ff9c?style=for-the-badge&logo=googlechrome&logoColor=black"/></a>
<a href="https://x.com/b4x0rn"><img src="https://img.shields.io/badge/X-@b4x0rn-000000?style=for-the-badge&logo=x&logoColor=white"/></a>
<a href="https://tryhackme.com"><img src="https://img.shields.io/badge/TRYHACKME-TOP_2%25-212C42?style=for-the-badge&logo=tryhackme&logoColor=white"/></a>
<img src="https://img.shields.io/badge/STATUS-LEARNING_%26_BREAKING-00ff9c?style=for-the-badge&labelColor=0d1117"/>

<br/>

<img src="https://img.shields.io/badge/OSCP-TARGET-d73a49?style=flat-square&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/CRTP-IN_PROGRESS-f0883e?style=flat-square&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/CRTA-CERTIFIED-00ff9c?style=flat-square&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/MCRTA-CERTIFIED-00ff9c?style=flat-square&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/AD--RTS-CERTIFIED-00ff9c?style=flat-square&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/CAPT-CERTIFIED-00ff9c?style=flat-square&labelColor=0d1117"/>

</div>

---

## 🖥️ `root@b4x0rn:~#`

```console
root@b4x0rn:~# whoami
b4x0rn

root@b4x0rn:~# cat profile.yml
role:        Offensive Security Practitioner
focus:       Active Directory · Red Team · Web · Linux Privesc
certified:   CAPT · AD-RTS · MCRTA · CRTA
in_progress: CRTP
next_target: OSCP
scripting:   Bash · Python
mindset:     Always improving. Always learning. No limits.

root@b4x0rn:~# ./status.sh
[+] Labs ............... running
[+] Writeups ........... publishing
[+] TryHackMe .......... Top 2%  →  chasing Top 1%
[+] Certification path . CRTP → OSCP
```

---

## 🧭 Methodology

```mermaid
flowchart LR
    A([🔎 Recon]) --> B([📡 Enumeration])
    B --> C([💥 Initial Access])
    C --> D([⬆️ Privilege Escalation])
    D --> E([🔀 Lateral Movement])
    E --> F([👑 Domain Compromise])
    F --> G([📝 Reporting])
    style A fill:#0d1117,stroke:#00ff9c,color:#c9d1d9
    style B fill:#0d1117,stroke:#00ff9c,color:#c9d1d9
    style C fill:#0d1117,stroke:#00ff9c,color:#c9d1d9
    style D fill:#0d1117,stroke:#00ff9c,color:#c9d1d9
    style E fill:#0d1117,stroke:#00ff9c,color:#c9d1d9
    style F fill:#0d1117,stroke:#00ff9c,color:#c9d1d9
    style G fill:#0d1117,stroke:#00ff9c,color:#c9d1d9
```

---

## ⚔️ Technical Focus

<table>
<tr>
<td width="50%" valign="top">

#### 🏰 Active Directory
Domain enumeration · attack-path analysis · credential abuse · lateral movement
`impacket`

#### 🌐 Web Application
XSS · SQL injection · IDOR · content discovery · fuzzing
`burpsuite` `ffuf`

</td>
<td width="50%" valign="top">

#### 🐧 Linux & Network
Service discovery · enumeration · privilege escalation
`nmap` `bash`

#### ☁️ Cloud & Automation
Cloud red team fundamentals (MCRTA) · tooling & workflow scripting
`python` `bash`

</td>
</tr>
</table>

---

## 🛠️ Toolkit

<div align="center">

<img src="https://skillicons.dev/icons?i=linux,kali,bash,python,git,github,vscode,docker&theme=dark" />

<br/><br/>

<img src="https://img.shields.io/badge/Nmap-0E83CD?style=for-the-badge&logo=nmap&logoColor=white"/>
<img src="https://img.shields.io/badge/Burp_Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white"/>
<img src="https://img.shields.io/badge/ffuf-1F2937?style=for-the-badge&logo=gnometerminal&logoColor=00ff9c"/>
<img src="https://img.shields.io/badge/Impacket-8B0000?style=for-the-badge&logo=python&logoColor=white"/>

</div>

<details>
<summary><b>⌨️ Daily-driver workflow (click to expand)</b></summary>

```bash
# 1. Recon: full TCP sweep, then targeted service scan
nmap -p- --min-rate 5000 -oN full.txt <target>
nmap -sC -sV -p <ports> -oN services.txt <target>

# 2. Web: content & vhost discovery
ffuf -u http://<target>/FUZZ -w <wordlist> -mc all -fc 404
ffuf -u http://<target>/ -H "Host: FUZZ.<domain>" -w <wordlist> -fs <size>

# 3. Active Directory: authenticated enumeration with Impacket
impacket-GetUserSPNs <domain>/<user>:<pass> -dc-ip <dc> -request
impacket-secretsdump <domain>/<user>:<pass>@<dc>
```

*Authorized targets and lab environments only.*

</details>

---

## 📜 Certifications & Roadmap

| Status | Certification | Domain |
|:-:|:--|:--|
| ✅ | **CAPT** | Penetration testing · Hackviser |
| ✅ | **AD-RTS** | Active Directory red team |
| ✅ | **MCRTA** | Cloud red team |
| ✅ | **CRTA** | Active Directory red team |
| 🔄 | **CRTP** | Active Directory red team · *in preparation* |
| 🎯 | **OSCP** | Offensive security · *target* |

```mermaid
flowchart LR
    A[CAPT] --> B[AD-RTS] --> C[MCRTA] --> D[CRTA] --> E{{CRTP}} --> F{{OSCP}}
    style A fill:#0f3d2e,stroke:#00ff9c,color:#fff
    style B fill:#0f3d2e,stroke:#00ff9c,color:#fff
    style C fill:#0f3d2e,stroke:#00ff9c,color:#fff
    style D fill:#0f3d2e,stroke:#00ff9c,color:#fff
    style E fill:#0d1117,stroke:#f0883e,color:#fff,stroke-dasharray: 4 3
    style F fill:#0d1117,stroke:#d73a49,color:#fff,stroke-dasharray: 4 3
```

---

## 📊 GitHub Analytics

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=x0ph3nt&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00ff9c&icon_color=00ff9c&text_color=c9d1d9"/>
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=x0ph3nt&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00ff9c&text_color=c9d1d9"/>

<img src="https://streak-stats.demolab.com/?user=x0ph3nt&theme=tokyonight&hide_border=true&background=0d1117&ring=00ff9c&fire=00ff9c&currStreakLabel=00ff9c"/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=x0ph3nt&bg_color=0d1117&color=00ff9c&line=00ff9c&point=ffffff&area=true&area_color=00ff9c&hide_border=true" width="100%"/>

<img src="https://github-profile-trophy.vercel.app/?username=x0ph3nt&theme=nord&no-frame=true&no-bg=true&row=1&column=6&margin-w=8"/>

</div>

<!-- Optional: enable .github/workflows/snake.yml, then uncomment the block below
<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/x0ph3nt/x0ph3nt/output/github-snake-dark.svg" />
  <img alt="snake" src="https://raw.githubusercontent.com/x0ph3nt/x0ph3nt/output/github-snake.svg" />
</picture>
</div>
-->

---

## 📝 Research & Writeups

Attack-path breakdowns, lab notes, and technical writeups:

<div align="center">

### 🔗 [x0ph3nt.com](https://x0ph3nt.com)

</div>

---

## 🤝 Connect

<div align="center">

<a href="https://x.com/b4x0rn"><img src="https://img.shields.io/badge/DM_ME_ON_X-000000?style=for-the-badge&logo=x&logoColor=white"/></a>
<a href="https://x0ph3nt.com"><img src="https://img.shields.io/badge/READ_MY_WRITEUPS-00ff9c?style=for-the-badge&logo=googlechrome&logoColor=black"/></a>

<br/><br/>

```python
while True:
    learn(); practice(); break_things(); improve()
```

<!-- <sub>⚠️ For authorized testing and educational purposes only.</sub> -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00ff9c,55:0f3d2e,100:0d1117&height=120&section=footer" width="100%"/>

</div>
