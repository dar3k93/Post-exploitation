# Shell Spawnig

- [Python shell spawnig](#python)
- [vi shell spawnig](#vi)
- [bash shell spawnig](#bash)
- [Echo shell spawnig](#echo)
- [Perl shell spawnig](perl)

## python
- python -c 'import pty; pty.spawn("/bin/sh")'
- python3 -c 'import pty; pty.spawn("/bin/sh")'

## vi
- :!bash

## bash
- /bin/bash -i

## sh
- /bin/sh -i

## echo
- echo 'os.system('/bin/bash')'

## perl
- perl -e 'exec "/bin/sh";'
