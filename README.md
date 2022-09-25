# dginhoux.cron

[![Maintainer](https://img.shields.io/badge/maintained%20by-dginhoux-e00000?style=flat-square)](https://www.dginhoux.fr/)
[![License](https://img.shields.io/github/license/dginhoux/ansible_role.dginhoux.cron?style=flat-square)](https://github.com/dginhoux/ansible_role.dginhoux.cron/blob/main/LICENSE)
[![Release](https://img.shields.io/github/v/release/dginhoux/ansible_role.dginhoux.cron?style=flat-square)](https://github.com/dginhoux/ansible_role.dginhoux.cron/releases)
[![Status](https://img.shields.io/github/workflow/status/dginhoux/ansible_role.dginhoux.cron/Ansible%20Molecule?style=flat-square&label=tests)](https://github.com/dginhoux/ansible_role.dginhoux.cron/actions?query=workflow%3A%22Ansible+Molecule%22)
[![Ansible Galaxy](https://img.shields.io/badge/ansible-galaxy-black.svg?style=flat-square&logo=ansible)](https://galaxy.ansible.com/dginhoux/)[![Ansible version](https://img.shields.io/badge/ansible-%3E%3D2.10-black.svg?style=flat-square&logo=ansible)](https://github.com/ansible/ansible)

This ansible role configure cron and create files in `/etc/cron.d`

**Platforms Supported**:

This role require a supported platform. 
It will skip node with unsupported platform to avoid any compatibility problem.
This behaviour can be bypassed by settings this variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36 |
| EL | 7, 8 |

## ⚠️ Requirements

Ansible >= 2.12.

### Ansible role dependencies

None.

## ⚡ Installation

### Install with Ansible Galaxy

```shell
ansible-galaxy install dginhoux.cron
```

### Install with git

If you do not want a global installation, clone it into your `roles_path`.

```bash
git clone https://github.com/dginhoux/ansible_role.dginhoux.cron dginhoux.cron
```

But I often add it as a submodule in a given `playbook_dir` repository.

```bash
git submodule add https://github.com/dginhoux/ansible_role.dginhoux.cron roles/dginhoux.cron
```

As the role is not managed by Ansible Galaxy, you do not have to specify the
github user account.

### ✏️ Example Playbook

Basic usage is:

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

## ⚙️ Role Variables

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




## Author Information

Dany GINHOUX