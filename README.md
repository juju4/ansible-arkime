[![Actions Status - Master](https://github.com/juju4/ansible-arkime/workflows/AnsibleCI/badge.svg)](https://github.com/juju4/ansible-arkime/actions?query=branch%3Amaster)
[![Actions Status - Devel](https://github.com/juju4/ansible-arkime/workflows/AnsibleCI/badge.svg?branch=devel)](https://github.com/juju4/ansible-arkime/actions?query=branch%3Adevel)

# arkime ansible role

A simple ansible role to setup arkime.
* https://arkime.com/
* https://raw.githubusercontent.com/arkime/arkime/main/release/README.txt

## Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.13

### Operating systems

Tested on Ubuntu 20.04, 22.04

## Example Playbook

Just include this role in your list.
For example

```
- host: myhost
  roles:
    - juju4.arkime
```

You probably want to review variables.

## Variables

TBD

## Continuous integration

```
$ pip install molecule docker
$ molecule test
$ MOLECULE_DISTRO=ubuntu:22.04 molecule test --destroy=never
```


## Troubleshooting & Known issues

TBD

## License

BSD 2-clause
