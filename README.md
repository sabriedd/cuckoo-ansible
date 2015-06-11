# cuckoo-ansible

Ansible playbook to install cuckoo sandbox on local machine.

For the moment, we are supporting only the following distribution :
  - Ubuntu 14.04 Trusty Thar LTS - desktop

More distribution might be added in the future, if you want to help, any distribution support is welcome and will be really appreciated.

This playbook will install the following librairies :

 - [cuckoo's librairies](http://docs.cuckoosandbox.org/en/latest/installation/host/requirements/#installing-python-libraries)
 - [yara](http://plusvic.github.io/yara/)
 - [ssdeep and pydeep](http://ssdeep.sourceforge.net/)

It will use QEMU/KVM as virtualization software.



### Requirements :

To use this, you'll need to install Ansible first
```bash
sudo pip install -I ansible==1.9.1
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

Those files are commented, so please refer to each of them in order to know how to configure your installation


### Usage :

```bash
ansible-playbook playbook.yml -i inventory.txt -k -K
```

the `-k` option is used for ssh password prompt

the `-K` option is used for sudo password prompt



### Cuckoo Configuration :

Now you have a cuckoo setup on your machine, prepare your guest machines.

please refer to [Preparing the Guest](http://docs.cuckoosandbox.org/en/latest/installation/host/configuration/)  and proceed with the rest of cuckoo's configuration
