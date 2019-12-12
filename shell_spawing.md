## Shell Spawnig

#### python
- python -c 'import pty; pty.spawn("/bin/sh")'
- python3 -c 'import pty; pty.spawn("/bin/sh")'

#### From within VI
- :!bash

#### bash
- /bin/bash -i

#### sh
- /bin/sh -i

#### Echo
- echo 'os.system('/bin/bash')'

#### Perl
- perl -e 'exec "/bin/sh";'
