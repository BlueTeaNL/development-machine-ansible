Run Ansible on a clean installation (Ubuntu 14.04)
==================================================

1. Install Ansible

```
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

2. Install Git

```
sudo apt-get install git
```

3. Generate SSH key

```
ssh-keygen -t rsa
```

4. Add the SSH key to Gitlab

```
cat ~/.ssh/id_rsa.pub
```

Go to http://gitlab.bluetea.nl -> Profile Settings -> SSH keys -> Add SSH key

5. Clone the Bluetea / Ansible GIT repository

```
git clone git@gitlab.bluetea.nl:bluetea/ansible.git
cd ansible
```

6. Copy the hosts file to the Ansible configuration directory

```
sudo cp hosts /etc/ansible/
```

7. Copy the virtual host configuration for Apache

```
sudo cp vars/apache2.yml.dist vars/apache2.yml
```

8. Run Ansible!

```
sudo ansible-playbook bluetea-dev-env.yml
```

8. Ready! :-)
