[![build-test](https://github.com/darkwizard242/ansible-role-mkcert/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-mkcert/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-mkcert/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-mkcert/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/47488?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/47488?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/47488?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-mkcert&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-mkcert) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-mkcert&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-mkcert) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-mkcert&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-mkcert) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-mkcert&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-mkcert) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-mkcert?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-mkcert?color=orange&style=flat-square)

# Ansible Role: mkcert

Role to install (_by default_) [mkcert](https://github.com/FiloSottile/mkcert) on **Debian/Ubuntu** and **EL** systems.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
mkcert_app: mkcert
mkcert_version: 1.4.4
mkcert_os: linux
mkcert_arch: amd64
mkcert_dl_url: https://github.com/FiloSottile/{{ mkcert_app }}/releases/download/v{{ mkcert_version }}/{{ mkcert_app }}-v{{ mkcert_version }}-{{ mkcert_os }}-{{ mkcert_arch }}
mkcert_bin_path: /usr/local/bin
mkcert_file_owner: root
mkcert_file_group: root
mkcert_file_mode: '0755'
```

### Variables table:

Variable          | Description
----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------
mkcert_app        | Defines the app to install i.e. **mkcert**
mkcert_version    | Defined to dynamically fetch the desired version to install. Defaults to: **1.4.4**
mkcert_os         | Defines os type. Used for obtaining the correct type of binaries based on OS type. Defaults to: **linux**
mkcert_arch       | Defines os architecture. Used to set the correct type of binaries based on OS System Architecture. Defaults to: **amd64**
mkcert_dl_url     | Defines URL to download the mkcert binary from.
mkcert_bin_path   | Defined to dynamically set the appropriate path to store mkcert binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
mkcert_file_owner | Owner for the binary file of mkcert.
mkcert_file_group | Group for the binary file of mkcert.
mkcert_file_mode  | Mode for the binary file of mkcert.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **mkcert**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.mkcert
```

For customizing behavior of role (i.e. specifying the desired **mkcert** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.mkcert
  vars:
    mkcert_version: 1.4.3
```

For customizing behavior of role (i.e. placing binary of **mkcert** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.mkcert
  vars:
    mkcert_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-mkcert/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.linkedin.com/in/ali-muhammad-759791130/).
