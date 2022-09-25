[![Maintainer](https://img.shields.io/badge/maintained%20by-dginhoux-e00000?style=flat-square)](https://github.com/dginhoux)
[![License](https://img.shields.io/github/license/dginhoux/ansible_role.cron?style=flat-square)](https://github.com/dginhoux/ansible_role.cron/blob/master/LICENSE)


# :computer: dginhoux.cron


## :scroll: Role description

This ansible role configure cron and create files in `/etc/cron.d`


## :nut_and_bolt: Requirements

### Supported platforms

This role require a supported platform. 
It will skip node with unsupported platform to avoid any compatibility problem.
This behaviour can be bypassed by settings this variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36 |
| EL | 7, 8 |


### Ansible version

Ansible >= 2.12


### Role dependencies

None.


## :inbox_tray: Installation

### Install with Ansible Galaxy

```shell
ansible-galaxy install dginhoux.cron
```

### Install with git

```shell
git clone https://github.com/dginhoux/ansible_role.cron dginhoux.cron
```


## :rocket: Usage

### Example playbook

```yaml
- hosts: all
  roles:
    - name: start role dginhoux.cron
      ansible.builtin.include_role:
        name: dginhoux.cron
      vars:
        cron:
          - file: hello
            state: present
            tasks:
              - cmdline: echo 'hello'
                day: '*'
                hour: '6'
                minute: '05'
                month: '*'
                name: say_hello
                state: present
                user: www-data
                weekday: '*'
        
```


## :factory: Role Variables

Variables are divided in three types.

The **default vars** section shows you which variables you may
override in your ansible inventory. As a matter of fact, all variables should
be defined there for explicitness, ease of documentation as well as overall
role manageability.

The **context variables** are shown in section below hint you
on how runtime context may affects role execution.

### Default variables
Role default variables from `defaults/main.yml` : 

| Variable Name | Value |
|---------------|-------|
| cron | - file: hello<br>  state: present<br>  tasks:<br>  - cmdline: echo 'hello'<br>    day: '*'<br>    hour: '6'<br>    minute: '05'<br>    month: '*'<br>    name: say_hello<br>    state: present<br>    user: www-data<br>    weekday: '*'<br> |

### Context variables

Those variables are located in `vars/*.yml` are used to handle OS differences ; One of theses is loaded dynamically during role
runtime using the `include_vars` module and set OS specifics variable's.

Variables loaded from `vars/main.yml` : 






## :man: Author

Dany GINHOUX