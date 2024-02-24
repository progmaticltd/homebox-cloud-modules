# homebox-cloud-modules

Modules to run homebox in the cloud, not included in the main distribution.

To use these roles, make sure the path, relative or absolute, is included in the _role\_path_ variable, for instance:

```ini
roles_path = .:{{ playbook_dir }}/../../common/roles/:/home/andre/git/homebox-cloud-modules
```

You can then run the role(s) using the dynamic role selection syntax, for instance:

```sh
ROLE=vultr ansible-playbook install.yml
```

## Current roles

## Vultr specific roles

### Role vultr-vm-cleanup

Clean-up and removes Vultr specific features not needed or that interferes with HomeBox.

### Role vultr-vm-instance

Create the whole collection to run HomeBox in Vultr: VPC, Firewall rules and the virtual machine.
