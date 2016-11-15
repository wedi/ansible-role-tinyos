TinyOS Role for Ansible
=======================
[![Build Status](https://travis-ci.org/wedi/ansible-role-tinyos.svg?branch=master)](https://travis-ci.org/wedi/ansible-role-tinyos)

This Ansible role installs [TinyOS](https://github.com/tinyos/tinyos-main/), [nesC](https://github.com/tinyos/nesc) and all requirements to compile and install a firmware on sensor nodes. Right now only the MSP430 microcontroller toolchain (e.g. used on the TelosB sensor module) is included as I'm currently using only that one. Open an issue if you need any others.

Requirements
------------

I have tested this role on Ubuntu 16.04 LTS only. Please [open an issue](https://github.com/wedi/ansible-role-tinyos/issues)
and tell me if it's working on other systems as well.

Role Variables
--------------

Using the following variables to adust the target directory for the TinyOS / nesC source code:
```YAML
src_target: '/usr/local/src'
tinyos_src_dir: '{{ src_target }}/tinyos'
nesc_src_dir: '{{ src_target }}/nesc'
```

Example Playbook
----------------

An example how to apply this role and change the install directory at the same time:
```YAML
- hosts: servers
  become: true

  roles:
     - { role: wedi.tinyos, src_target: ~/My/Working/Directory }
```

License
-------

This role is released under the terms of the [MIT](https://github.com/wedi/ansible-role-tinyos/blob/master/LICENSE) license.

Author Information
------------------

Hi, I'm Dirk from Essen, Germany. Software developer, student of business and computer science. I wrote this role to learn provisioning and configuration management with Ansible. I hope you find it useful. Feel free to [open an issue](https://github.com/wedi/ansible-role-tinyos/issues) or pull request if you are having any suggestions.
