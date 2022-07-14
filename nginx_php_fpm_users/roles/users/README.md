Role Name
=========

A role to create a user and set up public key auth from local machine

Role Variables
--------------

**user_to_create** Username of the newly user

Example Playbook
----------------

---
- hosts: php
  roles:
    - {role: users, user_to_create: user1 }
