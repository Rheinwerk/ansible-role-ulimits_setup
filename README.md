ulimits setup
=========

This role can be used to set up modified ulimits settings

[![Build Status](https://github.com/Rheinwerk/ansible-role-ulimits_setup/actions/workflows/ci.yml/badge.svg)](https://github.com/Rheinwerk/ansible-role-ulimits_setup/actions/workflows/ci.yml)

Requirements
------------

None.

Role Variables
--------------

Every setting is one variable with a default in `defaults/main.yml`; set only the ones that
differ. The defaults are the CenterDevice values.

| Variable | Default |
|---|---|
| `_ulimits_setup_limits` | `nofile` 65536, soft and hard, for every user (`*`) |

`_ulimits_setup_limits` is a list of `/etc/security/limits.conf` entries with the keys `domain`, `type`
(`soft`, `hard` or `-`), `item` (e.g. `nofile`, `nproc`, `memlock`) and `value`; see limits.conf(5).
The role also adds `session required pam_limits.so` to `/etc/pam.d/common-session` and
`common-session-noninteractive`.

Until v0.4.0 the role took one `_ulimits_setup` dict with the key `limits` instead.

Dependencies
------------

None.


Example Playbook
----------------

Only the limits differ from the defaults here:

    - hosts: servers
      vars:
        _ulimits_setup_limits:
          - domain: "*"
            type: "-"
            item: "memlock"
            value: "unlimited"
      roles:
         - { role: ulimits_setup, tags: [ 'ulimits_setup' ] }

License
-------

Please see LICENSE.

Author Information
------------------

Original author is [Daniel Schneller](https://github.com/dschneller) as member of the [Rheinwerk](https://github.com/Rheinwerk) project.

