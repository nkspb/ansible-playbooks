Role Name
=========

Role to install dnsmasq and configure it as a local DNS and DHCP server.

Requirements
------------

RHEL-based distribution

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Custom domain for hosts accessed with short names
**custom_domain**: internal.lan  

Upstream DNS servers for lookups on non-local domains
**upstream_dns**:
  - 8.8.8.8
  - 8.8.8.4

A range of DHCP addresses to assign to clients, lease time
**dhcp_range**: 192.168.0.50,192.168.0.150,12h

Leases database
**dhcp_leasefile**: /var/lib/dnsmasq/dnsmasq.leases

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: centos
      gather_facts: yes
      become: yes
      tasks:
        - include_role:
            name: dnsmasq
          vars:
            custom_domain: "internal.lan"
            upstream_dns:
              - 8.8.8.8
              - 8.8.8.4
          tags:
            - setup_dnsmasq
            - drop_dnsmasq