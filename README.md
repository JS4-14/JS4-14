# Johaan Shiju

**BSc Cybersecurity, Aston University — hunting a 2027/28 UK security placement.**

Blue-leaning generalist. Public work so far skews SOC/detection; actively running offensive security against my own detections to test that against genuine interest.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/johaanshiju/)

## Pinned Work

| Project | Status | What it proves | Stack |
|---|---|---|---|
| [Sigma Detection Rulepack](https://github.com/JS4-14/Cybersecurity-Portfolio/tree/main/sigma-rules-cross-platform) | Closed — both rules validated end-to-end on real captured telemetry, cross-platform (KQL + SPL) | Found and documented two real SIEM-conversion failure modes, not just "wrote a rule" | Sigma, Sysmon, KQL, SPL |
| [Home SOC Lab](https://github.com/JS4-14/Cybersecurity-Portfolio) | In progress — live AD domain up, Kerberoasting hash extraction underway | Full attack → detect loop: build the infra, run the attack, write the detection | VirtualBox, Windows Server AD, Sysmon, Impacket |
| [SOC Investigation Repository](https://github.com/JS4-14/Cybersecurity-Portfolio/tree/main/SOC-Portfolio) | Complete — 4 investigations | MITRE-mapped reasoning and containment calls, not just an IOC list | MITRE ATT&CK, Sysmon |
| [Aston × Warwick CTF](https://github.com/JS4-14/Cybersecurity-Portfolio/tree/main/aston-warwick-ctf) | 3rd place, team | Performs under competition pressure — crypto, forensics, stego | — |
| OverTheWire Bandit | Complete | Linux/bash/SSH fundamentals | Linux, Bash |

## Currently Building

Kerberoasting live-AD detection. Domain's up, SPN-registered target account created, first live ticket pulled (RC4, standing out against AES elsewhere in the session). Next: extract the hash as a low-privilege user, capture the request in Sysmon/Wireshark, write the Sigma rule for the downgrade signal, publish.

## Lab Architecture

```
┌──────────────────────┐   Kerberos (88/389/445)   ┌────────────────────────┐
│  Ubuntu — attacker    │ ─────────────────────────▶│  Windows Server — DC    │
│  Impacket              │                            │  AD DS + DNS + KDC      │
└──────────────────────┘                            │  windomain.local        │
                                                      └───────────┬────────────┘
                                                                  │ domain-joined
                                                      ┌───────────▼────────────┐
                                                      │  Win11 — client          │
                                                      │  Sysmon, Event ID 4769   │
                                                      └─────────────────────────┘
```

## Tools

[![Sigma](https://img.shields.io/badge/Sigma-E4405F?style=for-the-badge)](#) [![Sysmon](https://img.shields.io/badge/Sysmon-0078D6?style=for-the-badge&logo=windows&logoColor=white)](#) [![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-C8102E?style=for-the-badge)](#) [![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)](#) [![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](#) [![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)](#)
