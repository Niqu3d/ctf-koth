# ctf-koth
This is my basic cheatsheet for Koth


### Things to do at the start
keep in mind we are not allowed to remove or turn off any ports or serveices that would cause the other team to not be able to reach it, however restarting the service is only allowed if services needs to be restarted for updating
dont forget to google


## Recon
Ping the IP to make sure you can reach it
``` 
ping <Target_IP>
```
curl the IP at the start to maybe find something useful
```
curl <TARGET_IP>
```
nmap to find open ports
```
nmap -sC -Pn -sV -p- -oN ./nmap/initial <TARGET_IP>
```
gobuster to find possible extensions
```
gobuster dir -u <TARGET_IP> -w /usr/share/wordlists/dirbuster/ -x html,php,txt

```
see if telnet is open
``` 
telnet <TARGET_IP>
```
try basic webpage ports
``` 
80, 8080, 8000, 3000, 443, 80443, 40443 
```
once port scan is done make try the found ports in url
```
<TARGET_IP> : <PORT>
```
serch Metaspolit for any possible known vulns for the protocols
``` 
msfconsole
search <protocol>
use <exploit>
show options
set RHOST <TARGET_IP>
set RPORT <PORT>
show targets
run
```
