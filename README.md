# HackTheBox CTF Write-ups

Personal write-ups and methodology notes from [Hack The Box](https://www.hackthebox.com/) machines, organized by OS and difficulty.

## ⚠️ Disclaimer

- These notes are for **educational purposes only**, documenting my own progress through retired HTB machines.
- Per HTB's rules, **flag values are never published** here.
- Lab-specific secrets (passwords, NTLM/Kerberos hashes, private keys, tickets) found during each box are **redacted** (`<REDACTED>`) — only the technique and the commands used to obtain/abuse them are kept.
- Spawn the box yourself on HTB to reproduce the credentials and get your own flags.

## Structure

```
Windows/
├── Easy/
├── Medium/
└── Hard/
```

See [Windows/README.md](Windows/README.md) for the full list of machines and techniques covered.

## Tools referenced across write-ups

`nmap`, `crackmapexec`/`netexec`, `smbclient`, `smbmap`, `ldapsearch`, `rpcclient`, `BloodHound` / `bloodhound-python`, `impacket` suite (`GetNPUsers.py`, `GetUserSPNs.py`, `secretsdump.py`, `psexec.py`, `mssqlclient.py`, `ticketConverter.py`, `getTGT.py`, `getST.py`), `Rubeus`, `Certify` / `certipy-ad`, `PowerView`/`PowerSploit`, `Powermad`, `evil-winrm`, `hashcat`, `john`, `kerbrute`, `Responder`.

## License

Notes shared as-is for learning purposes. No warranty.
