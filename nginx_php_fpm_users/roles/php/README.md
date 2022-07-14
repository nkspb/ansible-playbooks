Role Name
=========

A role to install php-fpm and configure it to listen on specific TCP port.

Role Variables
--------------

**php_fpm_port** php-fpm port. Default: 9000

Example Playbook
----------------

---
- hosts: php
  roles:
    - { role: php, php_fpm_port: 9000 }
