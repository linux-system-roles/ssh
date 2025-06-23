Changelog
=========

[1.6.0] - 2025-06-23
--------------------

### New Features

- feat: Support this role in container environments and builds (#185)

### Bug Fixes

- fix: Avoid setting ansible_managed variable (#189)

### Other Changes

- ci: Bump sclorg/testing-farm-as-github-action from 3 to 4 (#182)
- ci: bump tox-lsr to 3.8.0; rename qemu/kvm tests (#183)
- ci: Add Fedora 42; use tox-lsr 3.9.0; use lsr-report-errors for qemu tests (#184)
- ci: Add support for bootc end-to-end validation tests (#186)
- tests: Update tests_all_options.yml to do bootc end-to-end validation (#187)
- ci: Use ansible 2.19 for fedora 42 testing; support python 3.13 (#188)
- refactor: Ansible 2.19 support (#191)

[1.5.3] - 2025-04-23
--------------------

### Other Changes

- ci: ansible-plugin-scan is disabled for now (#169)
- ci: bump ansible-lint to v25; provide collection requirements for ansible-lint (#172)
- ci: Check spelling with codespell (#173)
- ci: Add test plan that runs CI tests and customize it for each role (#174)
- ci: In test plans, prefix all relate variables with SR_ (#175)
- ci: Fix bug with ARTIFACTS_URL after prefixing with SR_ (#176)
- ci: several changes related to new qemu test, ansible-lint, python versions, ubuntu versions (#177)
- ci: use tox-lsr 3.6.0; improve qemu test logging (#178)
- tests: Add missing dependency on Fedora 42 (#179)
- ci: skip storage scsi, nvme tests in github qemu ci (#180)

[1.5.2] - 2025-01-09
--------------------

### Bug Fixes

- fix: Workaround for CentOS 10 issues in openssh (#167)

### Other Changes

- ci: Use Fedora 41, drop Fedora 39 (#165)
- ci: Use Fedora 41, drop Fedora 39 - part two (#166)

[1.5.1] - 2024-10-30
--------------------

### Other Changes

- ci: Add workflow for ci_test bad, use remote fmf plan (#157)
- ci: Fix missing slash in ARTIFACTS_URL (#158)
- ci: Add tags to TF workflow, allow more [citest bad] formats (#159)
- ci: ansible-test action now requires ansible-core version (#160)
- ci: add YAML header to github action workflow files (#161)
- refactor: Use vars/RedHat_N.yml symlink for CentOS, Rocky, Alma wherever possible (#163)

[1.5.0] - 2024-08-01
--------------------

### New Features

- Handle reboot for transactional update systems (#151)

### Other Changes

- ci: Add tft plan and workflow (#152)
- ci: Update fmf plan to add a separate job to prepare managed nodes (#154)
- ci: Bump sclorg/testing-farm-as-github-action from 2 to 3 (#155)

[1.4.1] - 2024-07-02
--------------------

### Bug Fixes

- fix: add support for EL10 (#149)

### Other Changes

- ci: ansible-lint action now requires absolute directory (#148)

[1.4.0] - 2024-06-11
--------------------

### New Features

- feat: Add new configuration options and remove false positives in the test (#142)

### Other Changes

- ci: use tox-lsr 3.3.0 which uses ansible-test 2.17 (#141)
- ci: tox-lsr 3.4.0 - fix py27 tests; move other checks to py310 (#144)
- ci: Add supported_ansible_also to .ansible-lint (#145)

[1.3.3] - 2024-04-04
--------------------

### Other Changes

- ci: fix python unit test - copy pytest config to tests/unit (#137)
- ci: Bump ansible/ansible-lint from 6 to 24 (#138)
- ci: Bump mathieudutour/github-tag-action from 6.1 to 6.2 (#139)

[1.3.2] - 2024-01-16
--------------------

### Other Changes

- ci: support ansible-lint and ansible-test 2.16 (#133)
- ci: Use supported ansible-lint action; run ansible-lint against the collection (#134)
- ci: Run Fedora/CentOS CI in GH Actions + unbreak debian buster CI run (#135)

[1.3.1] - 2023-12-12
--------------------

### Bug Fixes

- fix: Fix warning for using jinja templates in assert (#131)

### Other Changes

- ci: Add ALP-Dolomite var file (#123)
- ci: bump actions/github-script from 6 to 7 (#129)
- refactor: get_ostree_data.sh use env shebang - remove from .sanity* (#130)

[1.3.0] - 2023-11-30
--------------------

### New Features

- feat: support for ostree systems (#124)

### Other Changes

- ci: fix ansible-lint issue in tests_user_config.yml (#125)
- tests: Ensure backup/restore preserves file attributes (#126)

[1.2.3] - 2023-11-06
--------------------

### Other Changes

- build(deps): bump actions/checkout from 3 to 4 (#113)
- ci: ensure dependabot git commit message conforms to commitlint (#116)
- ci: use dump_packages.py callback to get packages used by role (#118)
- ci: tox-lsr version 3.1.1 (#120)
- ci: Fix implicit octal value in main.yml (#121)

[1.2.2] - 2023-09-07
--------------------

### Other Changes

- ci: Add markdownlint, test_html_build, and build_docs workflows (#108)

  - markdownlint runs against README.md to avoid any issues with
    converting it to HTML
  - test_converting_readme converts README.md > HTML and uploads this test
    artifact to ensure that conversion works fine
  - build_docs converts README.md > HTML and pushes the result to the
    docs branch to publish dosc to GitHub pages site.
  - Fix markdown issues in README.md
  
  Signed-off-by: Sergei Petrosian <spetrosi@redhat.com>

- docs: Make badges consistent, run markdownlint on all .md files (#109)

  - Consistently generate badges for GH workflows in README RHELPLAN-146921
  - Run markdownlint on all .md files
  - Add custom-woke-action if not used already
  - Rename woke action to Woke for a pretty badge
  
  Signed-off-by: Sergei Petrosian <spetrosi@redhat.com>

- ci: Remove badges from README.md prior to converting to HTML (#110)

  - Remove thematic break after badges
  - Remove badges from README.md prior to converting to HTML
  
  Signed-off-by: Sergei Petrosian <spetrosi@redhat.com>

[1.2.1] - 2023-07-19
--------------------

### Bug Fixes

- fix: Fix rendering Match/Host defaults when user provides their own (#104)
- fix: facts being gathered unnecessarily (#106)

### Other Changes

- docs: note on default config in case of drop-in support (#103)
- ci: ansible-lint - ignore var-naming[no-role-prefix] (#105)

[1.2.0] - 2023-06-23
--------------------

### New Features

- feat: add ssh_backup option with default true (#91)

### Other Changes

- ci: Add pull request template and run commitlint on PR title only (#99)
- ci: Rename commitlint to PR title Lint, echo PR titles from env var (#101)

[1.1.16] - 2023-05-26
--------------------

### Other Changes

- docs: Consistent contributing.md for all roles - allow role specific contributing.md section
- docs: remove unused Dependencies section in README

[1.1.15] - 2023-04-27
--------------------

### Other Changes

- ci: Add commitlint GitHub action to ensure conventional commits
- ci: Remove Debian stretch (9)
- test: check generated files for ansible_managed, fingerprint

[1.1.14] - 2023-04-13
--------------------

### Other Changes

- ansible-lint - use changed_when for conditional tasks (#84)

[1.1.13] - 2023-04-06
--------------------

### Bug Fixes

- Proper indent when lists are used in block (#80)
- add vars files for Rocky 8/9 (links) (#81)

### Other Changes

- fix shellcheck issues; fix ansible-lint issues in generation (#69)
- Add check for non-inclusive language (#64)
- Add README-ansible.md to refer Ansible intro page on linux-system-roles.github.io (#78)
- Fingerprint RHEL System Role managed config files (#79)

[1.1.12] - 2023-01-20
--------------------

### New Features

- none

### Bug Fixes

- ansible-lint 6.x fixes (#60)

### Other Changes

- none

[1.1.11] - 2022-09-27
--------------------

### New Features

- Add final version of the option RequiredRSASize (#53)

Update source template to match generated template

Add final name of the RequiredRSASize parameter

keeping the old version for backward compatibility.

Upstream commit:
https://github.com/openssh/openssh-portable/commit/54b333d1

### Bug Fixes

- none

### Other Changes

- none

[1.1.10] - 2022-09-19
--------------------

### New Features

- none

### Bug Fixes

- cast value to string in jinja macro (#50)

Some versions of jinja will not automatically convert values to
string in a `{{ ... }}` block, so use `| string` to ensure that
it is converted to string.

### Other Changes

- none

[1.1.9] - 2022-07-26
--------------------

### New Features

- add RSAMinSize parameter (#45)

### Bug Fixes

- none

### Other Changes

- changelog_to_tag action - github action ansible test improvements (#46)

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
- update to tox-lsr 2.4.0 - add support for ansible-test with docker
- CI: Add support for RHEL-9

[1.0.0] - 2021-02-12
--------------------

### Initial Release
