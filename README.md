ansible-role-rocket-pool
=========

Ansible role to deploy the Rocket Pool software stack for Ethereum 2.0 staking.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

- [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker/)

Usage
----------------

```
ansible-galaxy install -r requirements.yml
```

```
- hosts: servers
  roles:
    - { role: username.rolename, x: 42 }
```

License
-------

[BSD 3-Clause](LICENSE)
