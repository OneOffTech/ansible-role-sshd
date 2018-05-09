## SSH server

#### Preconfigured:

* Only connections with ssh key authentication are possible (no password login).
* `root` access is generally not allowed.
* Only users that are members of the `ssh_login` group can login through ssh.
* Port is switched from `22` to the indicated value from the ansible variable `secure_ssh_port`, which can be [specified conveniently](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#host-variables) in the `ansible.hosts` file.
* A link to download the `authorized_keys` file for ssh must be specified with the variable `ssh_authorized_keys`.

#### You can connect directly with

`ssh -p YOURPORT user@123.456.789.1`

or use an alias in your `.ssh/config` (recommended):
```
Host NAME
  Port YOURPORT
  User  user
  Hostname 123.456.789.1
```
