Role Name
=========

Role to install and configure vsftpd.

Role Variables
--------------

Allow anonymous access:
**anonymous_enable**: "YES|NO"
Default: "NO"

Allow local users login:
**local_enable**: "YES|NO"
Default: "YES"

Allow uploading:
**write_enable**: "YES|NO"
Default: "NO"

Example Playbook
----------------

    - hosts: localhost
      gather_facts: no
      become: yes
      tasks:
        - include_role:
            name: vsftpd
          vars:
            anonymous_enable: "yes"
            local_enable: "yes"
            write_enable: "yes"
          tags:
            - setup_vsftpd
            - drop_vsftpd