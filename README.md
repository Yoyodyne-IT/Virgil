# Virgil

Virgil is a collection of playbooks to guide you through the [circles of Hell](https://en.wikipedia.org/wiki/Inferno_(Dante)).

They are meant to deploy Lookyloo, Lacus, and Pandora.

# Requirements

* A machine running at least Ubuntu 24.04
* `ansible` user on the target machine(s), passwordless sudo

To make the `ansible` user passwordless sudo, create `/etc/sudoers.d/91-ansible-users`, and insert the following line:

```bash
ansible ALL=(ALL) NOPASSWD:ALL
```

* DNS records pointing to the target machine(s) for `lacus`, `lookyloo`, `monitoring, `and `pandora`

* Ansible [installed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-and-upgrading-ansible-with-pipx) on the machine you're running the playbooks from.

# Setup

1. Clone this repository to your local machine
2. Edit `inventory.yaml` with the DNS records you configured earlier
3. Copy `vars/api_keys.yml.sample` to `vars/api_keys.yml` and fill in the keys if you have one for the services listed.
4. Have a look at the files in `templates/` and configure accordingly if needed (you can always do it later)

# Install

```bash
ansible-playbook -i inventory.yaml -u ansible playbook_install_lacus.yaml
ansible-playbook -i inventory.yaml -u ansible playbook_install_lookyloo.yaml
ansible-playbook -i inventory.yaml -u ansible playbook_install_pandora.yaml
```

# Update

```bash
ansible-playbook -i inventory.yaml -u ansible playbook_update.yaml
```


