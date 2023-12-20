# ROLE dginhoux.cron



## DESCRIPTION

This ansible role configure `cron` and create tasks files in `/etc/cron.d`.


## REQUIREMENTS

#### SUPPORTED PLATFORMS

| Platform | Versions |
|----------|----------|
| Debian | all |
| EL | all |
| Fedora | all |
| Ubuntu | all |



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
- name: Playbook
  hosts: all
  tasks:
    - name: start role dginhoux.cron
      ansible.builtin.include_role:
        name: dginhoux.cron
```


## VARIABLES

#### DEFAULT VARIABLES

Default variables defined in `defaults/main.yml`

#### EXAMPLES VARIABLES

```yaml
cron_list:
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
cron_list_group: []
cron_list_host: []
```

NOTE : Theses 3 lists `cron_list`, `cron_list_group` and `cron_list_host` are merged. <br />
You can use the `_host` and `_group` lists to specify per host and/or per group content.


#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`

## AUTHOR

Dany GINHOUX - https://github.com/dginhoux



## LICENSE

MIT
