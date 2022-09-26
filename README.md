# :computer: ROLE dginhoux.cron

## :scroll: DESCRIPTION

This ansible role configure cron and create files in `/etc/cron.d`


## :nut_and_bolt: REQUIREMENTS

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


## :inbox_tray: INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.cron
```

#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.cron dginhoux.cron
```


## :rocket: USAGE

#### EXAMPLE PLAYBOOK

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


## :factory: VARIABLES
#### DEFAULT VARIABLES
Role default variables from `defaults/main.yml` : 

| Variable Name | Value |
|---------------|-------|
|cron | ```yaml - file: hello<br>  state: present<br>  tasks:<br>  - cmdline: echo 'hello'<br>    day: '*'<br>    hour: '6'<br>    minute: '05'<br>    month: '*'<br>    name: say_hello<br>    state: present<br>    user: www-data<br>    weekday: '*'<br> ``` |


#### CONTEXT VARIABLES

Those variables are located in `vars/*.yml` are used to handle OS differences ; One of theses is loaded dynamically during role
runtime using the `include_vars` module and set OS specifics variable's.





## :man: AUTHOR

[![Author](https://img.shields.io/badge/maintained%20by-dginhoux-e00000?style=flat-square)](https://github.com/dginhoux)


## :bookmark_tabs: LICENSE

[![License](https://img.shields.io/github/license/dginhoux/ansible_role.cron?style=flat-square)](https://github.com/dginhoux/ansible_role.cron/blob/master/LICENSE)