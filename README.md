ansible-zimbra-single
=====================

This role automates the process of installing single-server Zimbra Open Source Edition v8.8.15 on CentOS 8.

Requirements
------------

1) Must be a fresh CentOS 8 minimal installation
2) Ansible control node must have the "netaddr" Python module installed

    # python3 -m pip install netaddr

Role Variables
--------------

    zimbra_timezone: Asia/Singapore
    zimbra_fqdn: mail.example.com
    zimbra_admin_password: ansible@zimbra2020

Example Playbook
----------------

Create playbook similar below:

    # vi site.yml

    --- 
    - hosts: zimbra
      vars:
        zimbra_timezone: Asia/Singapore
        zimbra_fqdn: mail.example.com
        zimbra_admin_password: ansible@zimbra2020
      roles:
        - ansible-zimbra-single

Then run as follows:

    # ansible-playbook site.yml

License
-------

MIT License

Author Information
------------------

Author: Jan Cubillan<br/>
GitHub: https://github.com/jancubillan<br/>
