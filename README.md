# Ansible training

## Installation

This training was made by Python 3.6, Ansible 2.6 and Vagrant 2.1. You'll also require Virtualbox 5.2.

## Getting started

Open Terminal, cd to this directory (containing the `Vagrantfile` and this README file).

Type in `vagrant up`, and let Vagrant do its magic. (To connect to the VM use `vagrant ssh` just for fun)

Edit your hosts file, adding the line (optional):

```
192.168.1.10 nodejs.test
```

## Some commands

```bash
cd ansible
ansible multi -a "hostname"
ansible multi -a "df -h"
ansible multi -a "free -m"
ansible webservers -a "date"
```

## Provisioning

```bash
cd anisible
ansible-galaxy install -r requirements.yml
ansible-playbook ansible/playbooks/webserver_playbook.yml
```

Test the app by opening your browser and access http://nodejs.test (if you added the host, otherwise the IP address).

## Notes

* To shut down the virtual machine, enter `vagrant halt` in the Terminal in the same folder that has the `Vagrantfile`. To destroy it completely (if you want to save a little disk space, or want to rebuild it from scratch with `vagrant up` again), type in `vagrant destroy`.

### References

* https://github.com/geerlingguy/ansible-for-devops/tree/master/nodejs
* https://github.com/nickovivar/DevOps-Minichat