# cuckoo-ansible

Ansible playbook to install cuckoo sandbox on local machine.

It is

This will install the following librairies :

 - cuckoo's librairies
 - yara
 - pydeep


### Requirements :

To use this, you'll need to install Ansible first
```bash
sudo apt-get install ansible
```

Configure and fill in the forms properly in order to make a new user dedicated to cuckoo
```bash
sudo adduser cuckoo
```
Add your current user to the newly created `cuckoo` group
```bash
sudo usermod my_user -a -G cuckoo
```

Because Ansible use SSH to configure machine, you'll need to install an ssh server.
```bash
sudo apt-get install openssh-server
```

### Configuration :

modify the files
- `roles/cuckoo/defaults/main.yml`
- `roles/ssdeep/defaults/main.yml`
- `roles/yara/defaults/main.yml`
