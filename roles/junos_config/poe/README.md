poe
=========

This role will build the configuration for any device running Junos.

[![Build Status](https://travis-ci.com/packetferret/juniper_build_config.svg?branch=master)](https://travis-ci.com/packetferret/juniper_build_config)
[![Ansible Galaxy](https://galaxy.ansible.com/packetferret/juniper_build_config)](https://galaxy.ansible.com/packetferret/juniper_build_config)


Requirements
------------

No special requirements are needed to execute the role.

Role Variables
--------------

We will be using a few variables, my personal preference is to stage these variables in `host_vars` or `group_vars` of your Ansible project. Reference the structure of [this repository](https://github.com/packetferret/Ansible-Campus-Fabric-Core-Distribution-CRB/tree/master/files/ansible) as an example

This playbook expects that we use a root level object called `configuration` in our YAML files and set our `ansible.cfg` file to the following option: 

```
[defaults]
hash_behaviour=merge
```

This will create one dictionary, called `configuration`, that will host all configuration elements. Without declaring `hash_behaviour=merge`, Ansible will overwrite the dictionary after reading each yaml file holding a `configuration` item.

With all of that out of the way, let's talk about the variables available for the `poe` template.

## configuration directories and files

 directories to hold configuration files as they're generated

| Variable | Required | Default | Choices | Comments |
|---|---|---|---|---|
| configuration.poe | no | n/a | n/a | dictionary that hosts all poe-related items |
| configuration.poe.interface | no | n/a | n/a | list that holds all interfaces |

Dependencies
------------

There are no dependencies for this role

Example Playbook
----------------

    - hosts: all
      roles:
         - poe

License
-------

See license.md

Author Information
------------------

Calvin Remsburg
https://github.com/packetferret
