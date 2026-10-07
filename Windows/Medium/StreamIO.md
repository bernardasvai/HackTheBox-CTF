# StreamIO (Medium)

> **Note:** source notes for this box are incomplete — only the initial recon/foothold step was documented. Kept here for the index; will be expanded if revisited.

## Enumeration

```bash
nmap -sC -sV -p- <target>
```

```
53/tcp    open domain
80/tcp    open http          Microsoft IIS 10.0
88/tcp    open kerberos-sec  (Domain: streamIO.htb)
135/tcp   open msrpc
139/tcp   open netbios-ssn
389/tcp   open ldap          (Domain: streamIO.htb)
443/tcp   open ssl/http      (cert CN=streamIO, SAN: streamIO.htb, watch.streamIO.htb)
445/tcp   open microsoft-ds?
464/tcp   open kpasswd5?
593/tcp   open ncacn_http
636/tcp   open tcpwrapped
3268/tcp  open ldap
3269/tcp  open tcpwrapped
5985/tcp  open http          (WinRM)
9389/tcp  open mc-nmf
```

## Initial finding — SQL injection

The virtual host `watch.streamIO.htb` was found vulnerable to a classic UNION-based SQL injection:

```
1'union select 1,2,3,4,5,6-- -
```

This confirmed injectability and leaked the backend SQL Server version via the reflected output. Further exploitation (data extraction, credential recovery, and the path to a shell) was not captured in the original notes.

## To do if revisited

- Enumerate the injectable endpoint's columns/tables for credentials.
- Check for xp_cmdshell / UNC-based NTLM capture as in [Escape](Escape.md) and [Manager](Manager.md).
