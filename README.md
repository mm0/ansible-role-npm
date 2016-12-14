Ansible Role: NPM v1.0
===

[![Build Status](https://travis-ci.org/mm0/ansible-role-npm.svg?branch=master)](https://travis-ci.org/mm0/ansible-role-npm)


An Ansible role that sets up npm for nodejs, npm and optionally installs packages for you


Requirements
--

None 

Role Variables
--

Available variables are listed below, along with default values:

```yml
npm_modules:  # list of npm modules to install/remove
- name: npm
  state: latest # latest/present/absent
  global: yes # or no

node_version: 0.10 # defaults to 0.10, used to configure apt repository

distro: trusty # used to specify ubuntu distro
```

Dependencies
---
None 

Example Playbook
---
```yml
- hosts: webservers
  vars:
        - npm_modules_to_install:
            - name: npm
                state: latest
                global: yes
            - name: grunt-cli
                state: latest
                global: yes
  roles:
  - { role: ansible-role-npm, node_modules: "{{ npm_modules_to_install }}" }
```

License
---------------

BSD-2

Author Information
------------------

[Matt Margolin](mailto:matt.margolin@gmail.com)

[mm0](https://github.com/mm0) on github