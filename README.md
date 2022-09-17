Ansible Role : dginhoux.cron
=========

This ansible role configure cron and create files in `/etc/cron.d`


Requirements
------------

This role require a supported platform defined in `meta/main.yml`.
It will skip node with unsupported platform ; this behaviour can be bypassed by settings this variable `asserts_bypass=True`.



Role Variables
--------------

```yaml
cron:
  - file: test
    state: present
    tasks:
      - name: hello
        state: present
        user: www-data
        minute: "*/5"
        hour: *
        day: *
        month: *
        weekday: *
        cmdline: echo 'hello'
```


Dependencies
------------

none


Example Playbook
----------------



License
-------

BSD


Author Information
------------------

https://github.com/dginhoux/
