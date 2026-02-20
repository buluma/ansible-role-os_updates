# [Ansible role os_updates](#ansible-role-os_updates)

Ansible role to install OS updates.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-os_updates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-os_updates/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-os_updates/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-os_updates)|[![downloads](https://img.shields.io/ansible/role/d/buluma/os_updates)](https://galaxy.ansible.com/buluma/os_updates)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-os_updates.svg)](https://github.com/buluma/ansible-role-os_updates/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-os_updates/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  vars:
    os_updates_apt_upgrade: "safe"
  roles:
    - role: buluma.os_updates
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-os_updates/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: false
  become: true

  roles:
    - name: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-os_updates/blob/master/defaults/main.yml):

```yaml
---
# Possible Values
# ALWAYS = Always reboot after updates
# NEVER = Never reboot after updates
# NEEDED = Only reboot after Kernel changes
os_updates_reboot: "NEEDED"

# YUM
# define packages which should not upgraded
os_updates_yum_exclude: ""
os_updates_yum_clean_cache: true

# APT
os_updates_apt_upgrade: "safe"
# define packages which should not upgraded
os_updates_apt_exclude: []
os_updates_apt_autoremove: true

# reboot options
os_updates_reboot_delay: 30
os_updates_reboot_timeout: 300
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-os_updates/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-os_updates/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-os_updates/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-os_updates/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

