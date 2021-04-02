ansible-zimbra-single
=====================

This role automates the process of installing single-server Zimbra Open Source Edition v8.8.15 and v9.0.0 on CentOS 8 and Ubuntu 18.04.

Requirements
------------

1) Must be a fresh CentOS 8 or Ubuntu 18.04 minimal installation
2) Static network configuration must be already set
3) Ansible control node must have the "netaddr" Python module installed

Installing Ansible and "netaddr" module using PIP
-------------------------------------------------

    # python3 -m pip install ansible
    # python3 -m pip install netaddr

Role Variables
--------------

    zimbra_timezone: Asia/Singapore
    zimbra_fqdn: mail.example.com
    zimbra_admin_password: zimbra4ever

Example Playbook
----------------

Create playbook similar below:

    # vi site.yml

    --- 
    - hosts: zimbra
      vars:
        zimbra_timezone: Asia/Singapore
        zimbra_fqdn: mail.example.com
        zimbra_admin_password: zimbra4ever
      roles:
        - ansible-zimbra-single

Then run as follows:

    # ansible-playbook site.yml --tags install

If you want to setup Zimbra 9 instead:

    # ansible-playbook site.yml --tags zimbra9

Other Features
--------------

The role also installs Fail2Ban configured with predetermined jails and filters. You can view them in /etc/fail2ban directory.

    # fail2ban-client status
      Status
      |- Number of jail:	4
      `- Jail list:	sshd, zimbra-admin, zimbra-smtp, zimbra-webmail

License
-------

MIT License

Author Information
------------------

Author: Jan Cubillan<br/>
GitHub: https://github.com/jancubillan<br/>
