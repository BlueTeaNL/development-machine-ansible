BlueTea Ansible IT Automation
============================

This repository contains Ansible configurations for automating server installations and application deployments.

This repository is still a work in progress so it isn't finished yet!

## Requirements

Make sure you use a SSH KEY which is authorized to log in at the root account.
To prevent Ansible asking for the password of the ssh key, start an ssh agent.

```
ssh-agent bash
ssh-add ~/.ssh/id_rsa
```

## General

Before executing playbooks you should have ansible installed. The ansible control machine has to be a Linux machine (Ubuntu / CentOS / ...). In Ubuntu run `apt-get install ansible` to install Ansible. Make sure you have installed the Ansible PPA otherwise you get an ancient version! Run `apt-add-repository ppa:ansible/ansible` and `apt-get update` before installing ansible.

After the installation process has finished configure the hosts. The general configuration files are located in the `/etc/ansible` directory. The `hosts` file contains all hosts. This repository conatins an example hosts file you can use.

## Playbooks

### Development Machine

Ansible can setup a new development machine in a matter of minutes. This playbook contains the following packages:
* Apache2
* PHP 5.4
* MySQL server
* Supervisor
* RabbitMQ
* MongoDB
* PhpMyAdmin
* Samba share connected to /var/www

Run this playbook by executing `ansible-playbook bluetea-dev-env.yml`

**This playbook is a WIP**

### CloudVPS Backup to Object Store Script (boss)

The CloudBPS Backup to Object Store Script is a BETA backup script to there OpenStack Swift (Object Store) environment. Pim is enrolled in the BETA testing program and will create an Ansible role for this script.
The playbook will contain:
* Install package depedenceis
* Install / Update CloudVPS-boss script
* Create nescassary settings

Run this playbook by executing `ansible-playbok cloudvps-boss.yml`

## Changelog

Check the [changelog file](CHANGELOG.md) for the latest changes and versions
