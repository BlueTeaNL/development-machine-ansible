Run Ansible on a clean installation (Ubuntu 14.04)
==================================================

#### Install Ansible

```
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

#### Install Git

```
sudo apt-get install git
```

#### Generate SSH key

```
ssh-keygen -t rsa
```

#### Add the SSH key to Gitlab

```
cat ~/.ssh/id_rsa.pub
```

Go to http://gitlab.bluetea.nl -> Profile Settings -> SSH keys -> Add SSH key

#### Clone the Bluetea / Ansible GIT repository

```
git clone git@gitlab.bluetea.nl:bluetea/ansible.git
cd ansible
```

#### Copy the hosts file to the Ansible configuration directory

```
sudo cp hosts /etc/ansible/
```

#### Copy the virtual host configuration for Apache

```
sudo cp vars/apache2.yml.dist vars/apache2.yml
```

#### Run Ansible!

```
sudo ansible-playbook bluetea-dev-env.yml
```

#### Ready! :-)
