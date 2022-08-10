ginhouxnet.cron
=========

This ansible role configure cron and create files in /etc/cron.d 


Requirements
------------

This ansible role will only run on identified OS defined on meta/main.yml


Role Variables
--------------

It's just a simple list like : 

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




Example Playbook
----------------



License
-------

BSD


Author Information
------------------

Dany GINHOUX
