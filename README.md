# dginhoux.cron

[![Ansible version](https://img.shields.io/badge/ansible-%3E%3D2.10-black.svg?style=flat-square&logo=ansible)](https://github.com/ansible/ansible)

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
git clone   dginhoux.cron
```

But I often add it as a submodule in a given `playbook_dir` repository.

```bash
git submodule add  roles/dginhoux.cron
```

As the role is not managed by Ansible Galaxy, you do not have to specify the
github user account.

### ✏️ Example Playbook

Basic usage is:

```yaml
- hosts: all
  roles:
    - role: dginhoux.cron
      vars:
        cron: []
        
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
Role default variables from `defaults/main.yml`.

| Variable Name | Value |
|---------------|-------|
| cron | []<br> |

### Context variables

Those variables from `vars/*.yml` are loaded dynamically during task
runtime using the `include_vars` module.

Variables loaded from `vars/main.yml`.





## Author Information

Dany GINHOUX