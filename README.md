ansible-zimbra-single
=====================

This role automates the process of installing single-server Zimbra Open Source Edition v8.8.15 on CentOS 8.

Requirements
------------

1) Must be a fresh CentOS 8 minimal installation
2) Static network configuration must be already set
3) This role will be pulled and run on the same server where Zimbra will be installed

Role Variables
--------------

Modify the variables in vars/main.yml to suit your environment.

Dependencies
------------

1) Static Networking
2) Ansible Engine

Example Playbook
----------------

Create an inventory file similar below:

    # vi inventory

    [all:vars]
    ansible_user=root
    ansible_connection=local

    [server]
    localhost

Create playbook similar below:

    # vi site.yml

    --- 
    - hosts: server
      roles:
        - jancubillan.ansible_zimbra_single

Then run as follows:

    # ansible-playbook -i inventory site.yml

License
-------

MIT License

Author Information
------------------

Author: Jan Cubillan<br/>
GitHub: https://github.com/jancubillan<br/>
Ansible Galaxy: https://galaxy.ansible.com/jancubillan
