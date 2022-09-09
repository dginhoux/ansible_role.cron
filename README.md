ginhouxnet.cron
=========

This ansible role configure cron and create files in `/etc/cron.d`


Requirements
------------

This role is built to only run on platforms defined in `meta/main.yml`


Role Variables
--------------


```
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
