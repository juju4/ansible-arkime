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

* librdkafka dependency issue in 4.3.0 on ubuntu 22.04 and fixed version unreleased = use 4.2.0
https://github.com/arkime/arkime/commit/f648d6cdce58fb48bbcb90d86b1e1cb4a2ed1157 unreleased 4.3.1 fix ubuntu22 kafka dep

* Github hosted images run on VirtualPC virtualization and likely don't allow network card promiscuous mode aka network capture.
```
+ /opt/arkime/bin/arkime_config_interfaces.sh -c /opt/arkime/etc/config.ini -n default
RTNETLINK answers: Operation not permitted
RTNETLINK answers: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
netlink error: Operation not permitted
+ /opt/arkime/bin/capture -c /opt/arkime/etc/config.ini
Apr 28 19:16:37 main.c:214 parse_args(): WARNING: gethostname doesn't return a fully qualified name and getdomainname failed, this may cause issues when viewing pcaps, use the --host option - fv-az262-360
FATAL CONFIG ERROR - pcap open live failed! eth0: You don't have permission to capture on that device (socket: Operation not permitted)
```

## License

BSD 2-clause
