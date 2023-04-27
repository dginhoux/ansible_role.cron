# ROLE dginhoux.cron



## DESCRIPTION

This ansible role configure `cron` and create tasks files in `/etc/cron.d`.


## REQUIREMENTS

#### SUPPORTED PLATFORMS

This role require a supported platform.<br />
It will skip node with unsupported platform to avoid any compatibility problem.<br />
This behaviour can be bypassed by settings the following variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36, 37, 38 |
| EL | 7, 8 |

#### ANSIBLE VERSION

Ansible >= 2.13

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

Default variables defined in `defaults/main.yml` : 

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
#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`

## AUTHOR

Dany GINHOUX - https://github.com/dginhoux



## LICENSE

MIT
