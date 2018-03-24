ssh_opt_parse
=======================

Parse `ssh` command and its options.
A port number, user name, host name and the command will be detected.

```
./ssh_opt_parse ssh myuser@myhost
SSH_PORT        22
SSH_USER        myuser
SSH_HOST        myhost
SSH_COMMAND

./ssh_opt_parse ssh -o StrictHostKeyChecking=no -p 432 -t cac01 -l fuga ls -al hoge fuga
SSH_PORT        432
SSH_USER        fuga
SSH_HOST        cac01
SSH_COMMAND     ls -al hoge fuga
```

`~/.ssh/config` file is loaded automatically


`~/.ssh/config` :

```
Host host01
    Hostname 1.2.3.4
    User ubuntu
    Port 1234

Host host02
    User ubuntu
```

Then...

```
$ ./ssh_opt_parse ssh host01
SSH_PORT        1234
SSH_USER        ubuntu
SSH_HOST        host01
SSH_COMMAND

$ ./ssh_opt_parse ssh host02 -p 443 -t -o SomeOption=yes ping -c 1 host01
SSH_PORT        443
SSH_USER        ubuntu
SSH_HOST        host02
SSH_COMMAND     ping -c 1 host01
```
