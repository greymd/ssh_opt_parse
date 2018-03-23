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
