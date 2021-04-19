# How To Write Ansible Playbooks

This repository contains the examples and demos from the [How To Write Ansible Playbooks](https://www.digitalocean.com/community/tutorial_series/how-to-write-ansible-playbooks) Tutorial Series.

_Please notice that the playbooks in this repository are for demonstration and learning. They are not intended for production setups._

## Usage

To try these examples on your local Ansible setup, start by cloning this repository on your **Ansible Control Node**.

```command
git clone https://github.com/do-community/ansible-practice.git
cd ansible-practice
```

Edit the included `inventory` file to include your remote node(s):

```command
nano inventory
```

```ini

[dev]
203.0.113.10

[all:vars]
ansible_python_interpreter=/usr/bin/python3
```

Save and close the file. 

You can run the playbooks with:

```command
ansible-playbook -i inventory playbook-01.yml -u REMOTE_USER
```

If the playbook has a `become` directive it means you'll most probably will have to provide the `sudo` password for your connecting user. You dan do that by including the `-K` parameter:

```command
ansible-playbook -i inventory playbook-01.yml -u REMOTE_USER -K
```

For more details, please refer to the tutorial series: [How To Write Ansible Playbooks](https://www.digitalocean.com/community/tutorial_series/how-to-write-ansible-playbooks).
