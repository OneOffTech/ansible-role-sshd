## SSH server

#### Preconfigured:

* Only connections with ssh key authentication are possible (no password login).
* `root` access is generally not allowed.
* Only users that are members of the `ssh_login` group can login through ssh.
* Port is switched from `22` to the indicated value in the [`data`/`.env`](../../data/.env,example) file.

#### You can connect directly with

`ssh -p 2222 user@123.456.789.1`

or use an alias in your `.ssh/config` (recommended):
```
Host asososca
  Port 2222
  User  user
  Hostname 123.456.789.1
```
