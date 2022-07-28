Changelog
=========

[1.1.9] - 2022-07-26
--------------------

### New Features

- add RSAMinSize parameter (#45)

### Bug Fixes

- none

### Other Changes

- changelog_to_tag action - support other than "master" for the main branch name, as well (#46)

[1.1.8] - 2022-07-19
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- make all tests work with gather_facts: false (#39)

Ensure that all of the tests work when using ANSIBLE_GATHERING=explicit

- make min_ansible_version a string in meta/main.yml (#40)

The Ansible developers say that `min_ansible_version` in meta/main.yml
must be a `string` value like `"2.9"`, not a `float` value like `2.9`.

- Add CHANGELOG.md (#41)

[1.1.7] - 2022-05-18
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- Update CI and docs

[1.1.6] - 2022-05-06
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- bump tox-lsr version to 2.11.0; remove py37; add py310
- Fix Debian and Ubuntu CI

[1.1.5] - 2022-04-14
--------------------

### New Features

- support gather\_facts: false; support setup-snapshot.yml

### Bug Fixes

- none

### Other Changes

- bump tox-lsr version to 2.10.1

[1.1.4] - 2022-01-10
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- bump tox-lsr version to 2.8.3
- change recursive role symlink to individual role dir symlinks

[1.1.3] - 2021-12-06
--------------------

### New Features

- Add new configuration options from Openssh 8.7p1

### Bug Fixes

- none

### Other Changes

- Run the new tox test
- update tox-lsr version to 2.8.0

[1.1.2] - 2021-11-08
--------------------

### New Features

- support python 39, ansible-core 2.12, ansible-plugin-scan

### Bug Fixes

- none

### Other Changes

- update tox-lsr version to 2.7.1
- tests: Make sure openssh client package is installed before trying to use manual page for ssh\_config

[1.1.1] - 2021-09-21
--------------------

### New Features

- none

### Bug Fixes

- Use {{ ansible\_managed | comment }} to fix multi-line ansible\_managed

### Other Changes

- use apt-get install -y
- use tox-lsr version 2.5.1

[1.1.0] - 2021-08-10
--------------------

### New Features

- Drop support for Ansible 2.8 by bumping the Ansible version to 2.9

### Bug Fixes

- none

### Other Changes

- Clean up Ansible 2.8 CI configuration entries

[1.0.2] - 2021-06-10
--------------------

### New Features

- none

### Bug Fixes

- Fix variable precedence for ssh\_drop\_in\_name

### Other Changes

- none

[1.0.1] - 2021-04-07
--------------------

### New Features

- none

### Bug Fixes

- Fix ansible-test errors
- README: Fix ssh\_drop\_in\_name option description

### Other Changes

- Remove python-26 environment from tox testing
- update to tox-lsr 2.4.0 - add support for ansible-test sanity with docker
- CI: Add support for RHEL-9

[1.0.0] - 2021-02-12
--------------------

### Initial Release
