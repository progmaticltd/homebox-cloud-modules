## Purpose

Remove features not needed to run HomeBox, especially before the system installation.

Use the following command line to run the role:

```sh
ROLE=vultr-vm-cleanup ansible-playbook install.yml
```

This will stop and remove some services used by Vultr, Remove some packages and log files as well.
