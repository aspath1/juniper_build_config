build_directories
=========

This role will build directories to hold the configurations as they're being constructured.

[![Build Status](https://travis-ci.com/packetferret/juniper_build_config.svg?branch=master)](https://travis-ci.com/packetferret/juniper_build_config)
[![Ansible Galaxy](https://galaxy.ansible.com/packetferret/juniper_build_config)](https://galaxy.ansible.com/packetferret/juniper_build_config)


Requirements
------------

No special requirements are needed to execute the role.

Role Variables
--------------

We will be using a few variables, feel free to stage these variables in `host_vars` or `group_vars` of your Ansible project.

## configuration directories and files

 directories to hold configuration files as they're generated

| Variable | Required | Default | Choices | Comments |
|---|---|---|---|---|
| temporary_directory | yes | "/tmp/ansible/" | any path you like | root path to hold all configuration elements |
| build_directory | yes | "{{ temporary_directory }}/{{ inventory_hostname }}" | any path you like | a device-specific directory to hold configuration elements as they're built |
| build_directory_temp | yes | "{{ build_directory }}/tmp" | any path you like | path to hold stanzas as they're being generated |
| build_directory_complete | yes | "{{ build_directory }}/complete" | any path you like | path for the completed configuration to be stored |
| build_completed_file | yes | "{{ build_directory_complete }}/{{ inventory_hostname }}.conf" | any path you like | completed configuration file |

## backup directories and files

 directories to hold backup files as they're retreived

| Variable | Required | Default | Choices | Comments |
|---|---|---|---|---|
| backup_directory | yes | "./backup/{{ inventory_hostname }}" | any path you like | root path for backing up facts and configurations |
| backup_facts_directory | yes | "{{ backup_directory }}/facts" | any path you like | a device-specific directory to hold backup facts |
| backup_config_directory | yes | "{{ backup_directory }}/config" | any path you like | path to backup configurations |
| backup_file | yes | "{{ backup_config_directory }}/{{ inventory_hostname }}.conf" | any path you like | backup configuration file |

## bootstrap directories and files

 directories to hold bootstrap configurations

| Variable | Required | Default | Choices | Comments |
|---|---|---|---|---|
| bootstrap_config_dir | yes | "./backup/bootstrap" | any path you like | path for holding bootstrap configurations |
| bootstrap_config_file | yes | "{{ bootstrap_config_dir }}/{{ inventory_hostname }}.conf" | any path you like | a device-specific bootstrap file |

Dependencies
------------

There are no dependencies for this role

Example Playbook
----------------

Make sure to place this role in front of all configuration building roles that begin with `junos_`, they are counting on these directories to be present:

    - hosts: all
      roles:
         - build_directories

License
-------

See license.md

Author Information
------------------

Calvin Remsburg
https://github.com/packetferret
