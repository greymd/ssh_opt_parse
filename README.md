ssh_opt_parse
=======================

```
$ ./ssh_opt_parse ssh myuser@myhost
SSH_PORT        22
SSH_USER        myuser
SSH_HOST        myhost
SSH_CMD

$ ./ssh_opt_parse ssh -o StrictHostKeyChecking=no -p 432 -t cac01 -l fuga ls -al hoge fuga
SSH_PORT        432
SSH_USER        fuga
SSH_HOST        cac01
SSH_CMD  ls -al hoge fuga
```
