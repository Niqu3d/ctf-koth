# ctf-koth

### Things to do at the start
keep in mind we are not allowed to remove or turn off any ports or serveices that would cause the other team to not be able to reach it, however restarting the service is only allowed if services needs to be restarted for updating

## dont forget 
- dont forget to google
- dont forget to check what is locally installed, linux tool wise
- dont forget to make sure you have a system montior up
- dont forget to make sure you have event veiwers up



# table of contents
- [Recon](#recon)
- [RED team](#red-team)
- [Blue Team](#blue-team)
- [Elastic tips](#elastic-tips)
- [Kibana tips](#kibana-tips)
- [cheetsheets](https://github.com/Niqu3d/ctf-koth/tree/main/cheatsheets)
- [Extra Resources](#extra-resources)

# Recon
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
# RED team





# Blue Team

## Elastic tips
basic elastic curls
```
curl -X GET '<TARGET_IP>:9200/' 
add '?pretty' at the end to make it easier to read
```



## Kibana tips

Windows event log ids
``` 
4624 - sucessful login
4625 - login failed
4325 - user logoff
4646 - IKE Dos-prevention mode started
4648 - login was attemped using explicit credentials
4649 - a reply attack detected
4697 - a service was installed
4688 - a new process was created 
4720 - user account created
4722 - user account enabled
4723 - password change attempt
4724 - user account password set
4725 - user account disabled
4726 - user account deleted
4732 - local user account created
4738 - user account chaged
4739 - GPO changed
4740 - user account locked out
4767 - user account unlocked
4768 - kerberos TGT was requested
4771 - kerberos preauth failed
4722 - kerberos TGT request failed
6005 - event log was started
6006 - event log stopped
1102 - audit log was cleared
```

# Extra Resources
Links to useful other github resources 
## cheatsheets
- [ctf-koth-cheatsheet](https://github.com/pform-se/pform-ctf-koth-cheatsheet#resource)
- 

## awesome lists
- [awesome-ctf](https://github.com/apsdehal/awesome-ctf)
- [awesome-iocs](https://github.com/sroberts/awesome-iocs)
- [awesome-elastic](https://github.com/dzharii/awesome-elasticsearch)
- [awesome-security](https://github.com/sbilly/awesome-security)
- [the-art-of-hacking-list](https://github.com/The-Art-of-Hacking/h4cker)
- [CTF-Katana](https://github.com/JohnHammond/ctf-katana)
- 
