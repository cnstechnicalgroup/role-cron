Role: cns.cron
========

This role creates cron job entries for specified system user based on `cron_jobs` hash.

Requirements
------------

Nothing, it runs out of the box.

Role Variables
--------------

In the current version, you can specify the following variables:

| Name | Default | |
|------|---------|-|
| .name |   ---   | Name entry recorded in crontab, must be unique to hash |
| .minute |   ---   | Cron minute |
| .hour |   ---   | Cron hour |
| .day |   ---   | Cron day |
| .month |   ---   | Cron month |
| .weekday |   ---   | Cron weekday |
| .job |   ---   | Full job to execute |
| .user |   ---   | System user account to run job |
| .state |   ---   | present / absent |

Dependencies
------------

This package has no dependencies.

License
-------

GPLv2

Author Information
------------------

Sam Morrison (https://www.twitter.com/samcns)

Examples
--------

```yaml

# Set variables in var file

cron_jobs:
  - name: "Send Email Cron"
    minute: "*"
    hour: "*/1"
    day: "*"
    month: "*"
    weekday: "*"
    special_time: ""
    job: "/usr/bin/wget -O - -q https://{{ site_public_url }}/path/to/cron.php"
    user: "{{ system_user }}"
    state: "present

```
