## Purpose

The role vultr-vm-instance allows you, using the Vultr API, to create a full environment, that could be used both for
development and live systems.

### Configuration

You will need an API key from Vultr, and a minimal set of configuration, using YAML format.

### Export the Vultr key

```sh
export VULTR_API_KEY=74PM3DKBAW7WNP3XUPS4HHFXEUPDF1TUG66R
```

### Create the configuration file

```yml
ssh_keys:
  - name: default-ecdsa
    type: ecdsa-sha2-nistp384
    data: >-
	  AAAAE2VjZHNhLXNoYTItbmlzdHAzODQAAAAIbmlzdHAzODQAAABhBPT
	  za0dw8+vOnr+Ce5SgfFObgzve7X7uLKrBau67SgBwF/nua/F09lq3oz
	  UhM0hMMOvy5v61zlVbN2SesRt/4tKnBGdy1vzX0Eflq7ZFm2hmtsBxh
	  cWp3WucU0oFRv6eDg==
    comment: andre@lovelace
```

#### The SSH public key

The SSH key defined here will be copied as the administrator account, and used to connect on your virtual machine, so it
is important to choose wisely, and protect it with a passphrase.

You can split the key on multiple lines if you want, the key will be reassembled.

#### Define the VPC (Virtual Private Cloud)

```yml
# VPC settings
vpc:
  description: Homebox VPC
  subnet: 172.16.10.0/24
  region: ams
```

The most important parameter is the "region", so make sure it suits your needs and is close to your location.

#### Define the virtual machine

```yml
# Virtual machine settings
vm:
  plan: vc2-1c-2gb
  region: ams
  os: Debian 12 x64 (bookworm)

```

### Installation

Once everything has been defined, you can then create your virtual machine, using the following command line:

```sh
ROLE=vultr-vm-instance ansible-playbook install.yml
```

Note: The role supports _uninstallation_ as well, meaning the whole virtual machine, the VPC and the firewall will be
destroyed. This is meant for continuous integration purposes.
