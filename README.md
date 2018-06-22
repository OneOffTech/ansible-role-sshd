SSH-Server
=========

This roles sets up a ssh server with its configuration on a Debian (based) system. It is used for the [provision](https://github.com/oneofftech/provision) setup.

Requirements
----------------

* Ansible role [xamanu.user](https://galaxy.ansible.com/xamanu/user/)

Configuration
----------------

-* Only connections with ssh key authentication are possible (no password login).
-* `root` access is generally not allowed.
-* Only users that are members of the `ssh_login` group can login through ssh.
-* Port is switched from `22` to the indicated value from the ansible variable `secure_ssh_port`, which can be [specified conveniently](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#host-variables) in the `ansible.hosts` file.
-* A link to download the `authorized_keys` file for ssh must be specified with the variable `ssh_authorized_keys`.


This is work in progress and it is prefered to collaborate on it. Please communicate over the issue queue. Every pull request is highly appreciated.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: xamanu.essentials }



**You can connect directly with**: 

-`ssh -p YOURPORT user@123.456.789.1`

License
-------

MIT

Author Information
------------------

Felix Delattre - https://felix.delattre.de
