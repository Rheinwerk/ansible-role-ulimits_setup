ulimits setup
=========

This role can be used to set up modified ulimits settings

[![Build Status](https://github.com/Rheinwerk/ansible-role-ulimits_setup/actions/workflows/ci.yml/badge.svg)](https://github.com/Rheinwerk/ansible-role-ulimits_setup/actions/workflows/ci.yml)

Requirements
------------

None.

Role Variables
--------------

There is one main variable that drives this role: `_ulimits_setup`. It is a map that contains all configuration and settings for this role.
Please see `defaults/main.yml` for details.

Dependencies
------------

None.


Example Playbook
----------------

The general contract of this role is to take the variables map `_ulimits_setup` from `defaults/main.yml` as a template for your configuration and pass that configuration as a parameter to this role.

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      var:
        ULIMITS_SETUP:
          ...
      roles:
         - { role: ulimits_setup, tags: [ 'ulimits_setup' ], _ulimits_setup: "{{ ULIMITS_SETUP }}" }

License
-------

Please see LICENSE.

Author Information
------------------

Original author is [Daniel Schneller](https://github.com/dschneller) as member of the [Rheinwerk](https://github.com/Rheinwerk) project.

