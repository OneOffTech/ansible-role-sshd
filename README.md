SSH-Server
=========

This roles sets up a ssh server with its configuration on a Debian (based) system. It is used for the [provision](https://github.com/oneofftech/provision) setup.

Requirements
----------------

One or multiple users must be member of the `ssh_login` group. Group
Membership is not managed by this role.

SSH keys of the authorized users must be present in the
`~/.ssh/authorized_keys` file. Keys are not managed by this role.

Ansible role [xamanu.user](https://galaxy.ansible.com/xamanu/user/) may be
used to manage a default user with group membership and keys.

Configuration
----------------

-* Only connections with ssh key authentication are possible (no password login).
-* `root` access is generally not allowed.
-* Only users that are members of the `ssh_login` group can login through ssh.
-* The group can be configured via the `secure_ssh_group` variable.
-* Port is switched from `22` to the indicated value from the ansible variable `secure_ssh_port`, which can be [specified conveniently](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#host-variables) in the `ansible.hosts` file.


This is work in progress and it is prefered to collaborate on it. Please communicate over the issue queue. Every pull request is highly appreciated.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: xamanu.essentials }
```

**You can connect directly with**:

-`ssh -p YOURPORT user@123.456.789.1`

License
-------

MIT

Author Information
------------------

Felix Delattre - https://felix.delattre.de
