# sshd-create-certificate-authentification
ssh/sshd without password authentification (using certificate authentification)

```
ssh-keygen -t rsa
```
output: ```~/.ssh/id_rsa``` and ```~/.ssh/id_rsa.pub```
```
ssh user@remote-server mkdir -p .ssh

cat ~/.ssh/id_rsa.pub | ssh user@remote-server 'cat >> .ssh/authorized_keys'

ssh user@remote-server "chmod 700 .ssh; chmod 640 .ssh/authorized_keys"
```
testing with: ```ssh user@remote-server```
