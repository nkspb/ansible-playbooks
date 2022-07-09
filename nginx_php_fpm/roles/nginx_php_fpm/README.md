Role Name
=========

Role to install nginx with php-fpm.

Role Variables
--------------
Site domain name
**domain**: internal-site.com

Site root directory
**root**: /opt/nginx/ansible

nginx version to install
**nginx_version**: 1.18.0-6.1+deb11u2

php version to install
**php_version**: 2:7*.4+76

php-fpm version to install
**php_fpm_version**: 2:7.4+76

Example Playbook
----------------

  - hosts: localhost
    gather_facts: no
    become: yes
    tasks:
      - include_role:
          name: nginx_php_fpm
        vars:
          domain: internal-site.com
          root: /opt/nginx/ansible
          nginx_version: 1.18.0-6.1+deb11u2
          php_version: 2:7.4+76
          php_fpm_version: 2:7.4+76  
        tags:
          - setup
          - drop