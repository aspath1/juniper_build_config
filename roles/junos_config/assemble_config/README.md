assemble_config
=========

This role will assemble all smaller stanza files into a single Junos configuration file

[![Build Status](https://travis-ci.com/packetferret/juniper_build_config.svg?branch=master)](https://travis-ci.com/packetferret/juniper_build_config)
[![Ansible Galaxy](https://galaxy.ansible.com/packetferret/juniper_build_config)](https://galaxy.ansible.com/packetferret/juniper_build_config)


Requirements
------------

No special requirements are needed to execute the role.

Role Variables
--------------

We will be using a few variables, feel free to stage these variables in `host_vars` or `group_vars` of your Ansible project.

## assembling the configuration file

| Variable | Required | Default | Choices | Comments |
|---|---|---|---|---|
| temporary_directory | yes | "/tmp/ansible/" | any path you like | root path to hold all items |
| build_directory | yes | "{{ temporary_directory }}/{{ inventory_hostname }}" | any path you like | a device-specific directory to hold configuration elements as they're built |
| build_directory_temp | yes | "{{ build_directory }}/tmp" | any path you like | path to hold stanzas as they're being generated |
| build_directory_complete | yes | "{{ build_directory }}/complete" | any path you like | path for the completed configuration to be stored |
| build_completed_file | yes | "{{ build_directory_complete }}/{{ inventory_hostname }}.conf" | any path you like | completed configuration file |


Dependencies
------------

There are no dependencies for this role

Example Playbook
----------------

Make sure to place this role at the end of all configuration building roles.

    - hosts: all
      roles:
         - assemble_config

License
-------

See license.md

Author Information
------------------

Calvin Remsburg
https://github.com/packetferret
