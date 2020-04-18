NOT FOR PRODUCTION USE
======================

ansible-zimbra-single
=====================

This role automates the process of installing Zimbra Open Source Edition v8.8.15 on CentOS 7.

Requirements
------------

1) Static network configuration must be already configured on the server
2) Install Ansible Engine via EPEL or Python PIP
3) Run ansible-galaxy install jancubillan.ansible_zimbra_single

Role Variables
--------------

Modify the variables in vars/main.yml to suit your environment.

Dependencies
------------

1) Static Networking
2) Ansible Engine

Example Playbook
----------------

Copy the inventory and playbook at tests/inventory and tests/zimbra-single.yml. The playbook below should be similar.

    - hosts: server
      become: yes
      roles:
         - jancubillan.ansible_zimbra_single

How to use:

    # ansible-playbook -i inventory zimbra-single.yml

License
-------

BSD

Author Information
------------------

Author: Jan Cubillan<br/>
Github: https://github.com/jancubillan<br/>
Ansible Galaxy: https://galaxy.ansible.com/jancubillan
