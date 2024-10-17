Master Node Setup
Create a User on the Master Node:
```
useradd masterans
passwd masterans
```
Configure Sudo Privileges,Edit the sudoers file to allow ansadmin to run commands without a password.
```
visudo
```
```
Add the following line:
masterans ALL=(ALL) NOPASSWD: ALL
```
Configure SSH on Master,Enable password authentication by editing the SSH config file:
```
vi /etc/ssh/sshd_config
```
Set PasswordAuthentication to yes
```
passwordAuthentication yes
#permitEmptyPassword no
#Passwordauthentication no
```
Restart the SSH service:
```
service sshd restart
```

Install Ansible on Master Node:
```
amazon-linux-extras install ansible2
```
Generate SSH Keys for Ansible:
```
ssh-keygen
Save the keys in the default location (/home/masterans/.ssh/id_rsa), and skip setting a passphrase.
```
Copy the SSH Key to Worker Nodes
```
ssh-copy-id masterans@<workerans-ip>
```

Worker Node Setup
Create a User on Each Worker Node:
```
useradd workerans -m -d /home/aws/
passwd workerans
```
Configure SSH on Worker Node: Enable SSH by editing the configuration:
```
vi /etc/ssh/sshd_config
```
PasswordAuthentication is set to yes
```
passwordAuthentication yes
#permitEmptyPassword no
#Passwordauthentication no
```
restart sshd
```
systemctl reload sshd
```
Verify SSH Connectivity from Master to Worker Node
```
ssh masterans@<workerans-ip>
```


Configure Ansible on Master Node
```
cd /etc/ansible/
vi hosts
```
Add the IP address
```
[all]
<worker-node-ip>
```
Test the Connection with Ansible
```
ansible all -m ping
```
