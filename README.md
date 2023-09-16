# homebox-cloud-modules

Modules to run homebox in the cloud, not included in the main distribution.

To use these roles, make sure the path, relative or absolute, is included in the _role\_path_ variable, for instance:

```ini
roles_path = .:{{ playbook_dir }}/../../common/roles/:/home/andre/git/homebox-cloud-modules
```

## Current roles

- vultr: Cleanup vultr virtual machines _before_ installing homebox.
