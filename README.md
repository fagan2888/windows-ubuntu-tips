# Windows-ubuntu-tips

[Bash on Ubuntu on Windows][10] provides developers with a familiar Bash shell
and Linux environment on which to run most Linux command-line tools unmodified
without needed an entire Linux virtual machine

[10]: https://msdn.microsoft.com/en-us/commandline/wsl/about

## Setup Bash on Windows
```
lxrun /install
```

This guide uses [Ansible][20] an open-source automation engine that automates
software provisioning, configuration management, and application deployment.

## Setup the Ubuntu bash environment using Ansible

Start the bash environment
```
bash
```

### Install Ansible on Ubuntu
```
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

### Test the execution of Ansible on localhost
```
ansible all -i localhost, -c local -m ping
```

### Run Ansible as sudo on localhost
```
cd ansible
sudo ansible-playbook -i localhost, -c local playbook.yml
```

### Run Ansible as the logged in user to install user utilities
```
ansible-playbook -i localhost, -c local user-util-setup.yml
```

## Setup other utilities

## First login setup

1. Install legit git aliases
```
legit install
```

2. Install bash-it
```
~/.bash_it/install.sh
```

## Get Docker client binaries
```
mkdir docker
wget https://test.docker.com/builds/Linux/x86_64/docker-17.04.0-ce-rc1.tgz
tar -xvf docker-17.04.0-ce-rc1.tgz
cd docker
sudo cp docker /usr/local/bin
sudo cp completion/bash/docker /etc/bash_completion.d
```

## install bash-it
```
~/.bash_it/install.sh
bash-it enable completion docker
```
