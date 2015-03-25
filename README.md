Boostrap Ubuntu
==========================

This repository contains a basic Ansible role used for bootstrapping an Ubuntu server.

The included tasks are:

- Copy configuration files
- Configure locale
- Install and update Ubuntu packages
- Create a user(sudoer), assigning groups and public keys
- Basic security configuration:
    * Disable SSH root access
    * Disable password authentication
    * Install Fail2ban
- Install and configure Nullmailer with Mandrill

Forked from https://github.com/diec123/ansible-bootstrap and modified.


Requirements
------------
[Ansible](https://github.com/ansible/ansible) (1.2 above)


Role Variables
--------------

```
locale: en_GB.UTF-8
language: 'en_GB:en'
timezone: Europe/London

user_name: deploy
user_password: password
user_public_keys:
  - public_key1
  - public_key2 ....

ssh_port: 22

mandrill_user: user
mandrill_api_key: key

nullmailler_admin_mail: mail
nullmailer_domain: domain
```

Dependencies
------------
none.


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: mozodev.bootstrap-ubuntu }

License
-------

MIT License


