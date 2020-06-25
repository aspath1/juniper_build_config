protocols
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

With all of that out of the way, let's talk about the variables available for the `protocols` template.

## protocols configuration

| Variable | Required | Default | Choices | Comments |
|---|---|---|---|---|
| configuration.protocols | no | n/a | n/a | access-related items |
| configuration.protocols.mpls | no | n/a | n/a | MPLS configuration |
| configuration.protocols.bgp | no | n/a | n/a | BGP configuration |
| configuration.protocols.isis | no | n/a | n/a | IS-IS configuration |
| configuration.protocols.ldp | no | n/a | n/a | LDP configuration |
| configuration.protocols.evpn | no | n/a | n/a | EVPN configuration |
| configuration.protocols.l2_learning | no | n/a | n/a | L2 Learning configuration |
| configuration.protocols.lldp | no | n/a | n/a | LLDP configuration |
| configuration.protocols.lldp_med | no | n/a | n/a | LLDP-MED configuration |
| configuration.protocols.igmp_snooping | no | n/a | n/a | IGMP Snooping configuration |
| configuration.protocols.mstp | no | n/a | n/a | MSTP configuration |
| configuration.protocols.ospf | no | n/a | n/a | OSPF configuration |

Dependencies
------------

There are no dependencies for this role

Example Playbook
----------------


    - hosts: all
      roles:
         - protocols

License
-------

See license.md

Author Information
------------------

Calvin Remsburg
https://github.com/packetferret
