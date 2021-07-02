# Ansible Playbooks

This repository contains a list of parameterizable playbooks. Parameters are passed via environment variables.

## Prerequisites

Ansible must be installed

```bash
$ sudo apt-get install -y ansible
```

## Ansible Flags

```
-b become
-i inventory file
-l hosts group (from the inventory file)
-v verbose mode (logging)
```

## Parameterizable Playbooks

### APT Package Manager

Install Pakckages on a Debian based system

```bash
# Basic command syntax
$ NAME=<package_name> ansible-playbook playbook-apt.yml

# Examples
NAME="ansible" ansible-playbook -v -b -i inventory.txt -l my_group playbook-apt.yml
```

### Command

Execute commands and get the results

```bash
# Basic command syntax
$ CMD=<command> ansible-playbook playbook-cmd.yml

# Examples
CMD="uname -a" ansible-playbook -v -b -i inventory.txt -l my_group playbook-cmd.yml
```

### Copy

Copy files or directories to multiple remote hosts

```bash
# Basic command syntax
$ SRC=<local_path> DST=<remote_path> ansible-playbook playbook-cp.yml

# Examples
SRC=./info.txt DST="\$HOME/info.txt" ansible-playbook -v -b -i inventory.txt -l my_group playbook-cp.yml
```


### Fetch

Fetch files or directories from multiple remote hosts

```bash
# Basic command syntax
$ SRC=<local_path> DST=<remote_path> ansible-playbook playbook-fetch.yml

# Examples
SRC=./info.txt DST="\$HOME/info.txt" ansible-playbook -v -b -i inventory.txt -l my_group playbook-fetch.yml
```


### Shell

Fetch files or directories from multiple remote hosts

```bash
# Basic command syntax
$ [DEBUG=1] SRC=<local_path> DST=<remote_path> ansible-playbook playbook-shell.yml

# Examples
CMD="uname -a" ansible-playbook -v -b -i inventory.txt -l my_group playbook-shell.yml
DEBUG=1 CMD="apt-get update && apt-get upgrade" ansible-playbook -v -b -i inventory.txt -l my_group playbook-shell.yml
```
