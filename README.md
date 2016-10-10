# README.md

# Ansible Role: NPM v1.0

An Ansible role that sets up npm for nodejs 0.10 and installs packages for you

![travis-ci](https://travis-ci.org/mm0/ansible-role-npm.svg?branch=master)

## Requirements

None 

## Role Variables

Available variables are listed below, along with default values:

    npm_modules:  # list of npm modules to install/remove
    - name: npm
      state: latest # latest/present/absent
			global: yes # or no

## Dependencies

None 

## Example Playbook

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

## License

MIT

Author Information
------------------

[Matt Margolin](mailto:matt.margolin@gmail.com)

mm0 on github
