# Ansible training

## Installation

This training was made by Python 3.6, Ansible 2.6 and Vagrant 2.1. You'll also require Virtualbox 5.2.

## Getting started

Open Terminal, cd to this directory (containing the `Vagrantfile` and this README file).

Type in `vagrant up`, and let Vagrant do its magic. (To connect to the VM use `vagrant ssh` just for fun)

Edit your hosts file, adding the line:

```
127.0.0.1 nodejs.test
```

## Some commands

```bash
ansible multi -a "hostname" -i ansible/hosts
ansible multi -a "df -h" -i ansible/hosts
ansible --help
ansible multi -a "free -m" -i ansible/hosts
ansible webservers -a "date" -i ansible/hosts
```

## Provisioning

```bash
ansible-playbook ansible/playbooks/webserver_playbook.yml -i ansible/hosts
```

Test the app by opening your browser and access http://nodejs.test/

## Notes

* To shut down the virtual machine, enter `vagrant halt` in the Terminal in the same folder that has the `Vagrantfile`. To destroy it completely (if you want to save a little disk space, or want to rebuild it from scratch with `vagrant up` again), type in `vagrant destroy`.

#### References:
- https://github.com/geerlingguy/ansible-for-devops/tree/master/nodejs
- https://github.com/nickovivar/DevOps-Minichat