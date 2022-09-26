# ROLE dginhoux.cron



## DESCRIPTION

This ansible role configure `cron.d` and create tasks files in `/etc/cron.d`



## REQUIREMENTS

#### SUPPORTED PLATFORMS

This role require a supported platform. 
It will skip node with unsupported platform to avoid any compatibility problem.
This behaviour can be bypassed by settings this variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36 |
| EL | 7, 8 |

#### ANSIBLE VERSION

Ansible >= 2.12

#### DEPENDENCIES

None.



## INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.cron
```
#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.cron dginhoux.cron
```


## USAGE

#### EXAMPLE PLAYBOOK

```yaml
- hosts: all
  roles:
    - name: start role dginhoux.cron
      ansible.builtin.include_role:
        name: dginhoux.cron
```


## VARIABLES

#### DEFAULT VARIABLES
Role default variables from `defaults/main.yml` : 
```yaml
cron:
  - file: hello
    state: present
    tasks:
      - name: say_hello
        state: present
        user: www-data
        minute: "05"
        hour: "6"
        day: "*"
        month: "*"
        weekday: "*"
        cmdline: echo 'hello'
```
#### CONTEXT VARIABLES

Those variables are located in `vars/*.yml` are used to handle OS differences ; One of theses is loaded dynamically during role
runtime using the `include_vars` module and set OS specifics variable's.



## AUTHOR

[![Author](https://img.shields.io/badge/maintained%20by-dginhoux-e00000?style=flat-square)](https://github.com/dginhoux)



## LICENSE

[![License](https://img.shields.io/github/license/dginhoux/ansible_role.cron?style=flat-square)](https://github.com/dginhoux/ansible_role.cron/blob/master/LICENSE)
