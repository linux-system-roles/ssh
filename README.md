# ssh

![CI Testing](https://github.com/linux-system-roles/ssh/workflows/tox/badge.svg)
[![CI Ubuntu](https://github.com/linux-system-roles/ssh/actions/workflows/ansible-ubuntu.yml/badge.svg)](https://github.com/linux-system-roles/ssh/actions/workflows/ansible-ubuntu.yml)
[![CI Debian](https://github.com/linux-system-roles/ssh/actions/workflows/ansible-debian.yml/badge.svg)](https://github.com/linux-system-roles/ssh/actions/workflows/ansible-debian.yml)

An Ansible role for managing ssh clients configuration.

## Requirements

This role should work on any system that provides openssh client and is
supported by ansible. The role was tested on:

* RHEL/CentOS 6, 7, 8, 9
* Fedora
* Debian
* Ubuntu

## Role Variables

By default, the role should not modify the system configuration and generate
global `ssh_config` that matches OS default (the generated configuration does
not keep comments and order of the options).

### ssh_user

By default (`null`) the role will modify the global configuration for all
users. Other values will be interpreted as a username and the role will
modify per-user configuration stored under `~/.ssh/config` of the given user.
The user needs to exist before invoking this role otherwise it will fail.

### ssh_skip_defaults

By default (`auto`), the role writes the system-wide configuration file
`/etc/ssh/ssh_config` and keeps OS defaults defined there (*true*). This is
automatically disabled, when a drop-in configuration file is created
(`ssh_drop_in_name!=null`) or when per-user configuration file is created
(`ssh_user!=null`).

### ssh_drop_in_name

This defines the name for the drop-in configuration file to be placed in
system-wide drop-in directory. The name is used in the template
`/etc/ssh/ssh_config.d/{name}.conf` to reference the configuration file to
be modified. If the system does not support drop-in directory, setting this
option will make the play fail. Default is `null` if the system does not
support drop in directory and `00-ansible` otherwise.

The suggested format is `NN-name`, where `NN` is two-digit number used for
sorting the and `name` is any descriptive name for the content or the owner
of the file.

### ssh dict

A dict containing configuration options and respective values. See example
below.

* `ssh_...`:

Simple variables consisting of the option name prefixed with `ssh_` can be
used rather than a dict above. The simple variable overrides values in dict
above.

### ssh_additional_packages

This role automatically installs packages needed for most common use cases
on given platform. If some additional packages need to be installed (for
example `openssh-keysign` for host-based authentication), they can be specified
in this variable.

### ssh_config_file

The configuration file that will be written by this role. The default is
defined by template `/etc/ssh/ssh_config.d/{name}.conf` if system has drop-in
directory or `/etc/ssh/ssh_config` otherwise. If `ssh_user!=null`, the
default is `~/.ssh/config`.

### ssh_config_owner, ssh_config_group, ssh_config_mode

The owner, group and mode of the created configuration file. The files are
owned by `root:root` with mode `0644` by default, unless
`ssh_user!=null`. In that case, the mode is `0600` and owner and
group are derived from username given in `ssh_user` variable.

## Example Playbook

The following playbook configures the `root` user ssh configuration in his
<!--- wokeignore:rule=master -->
home directory to use compression, control-master multiplexing and enable
GSSAPI authentication in the "match final all" block. Additionally, it
creates alias "example" for connecting to the example.com host as a user
somebody. The last line disables X11 forwarding.

```yaml
- name: Manage ssh clients
  hosts: all
  tasks:
  - name: Configure ssh clients
    include_role:
      name: linux-system-roles.ssh
    vars:
      ssh_user: root
      ssh:
        Compression: true
        # wokeignore:rule=master
        ControlMaster: auto
        ControlPath: ~/.ssh/.cm%C
        Match:
          - Condition: "final all"
            GSSAPIAuthentication: true
        Host:
          - Condition: example
            Hostname: example.com
            User: somebody
      ssh_ForwardX11: false
```

More examples are in the [`examples/`](examples) directory.

## License

LGPLv3, see the file LICENSE for more information.

## Author Information

Jakub Jelen, 2021 - 2022
