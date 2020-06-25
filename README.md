# juniper_build_config

[![N|Solid](https://upload.wikimedia.org/wikipedia/commons/3/31/Juniper_Networks_logo.svg)](https://www.juniper.net/documentation/solutions/en_US/campus)

[![Build Status](https://travis-ci.org/packetferret/Ansible-juniper_build_config.svg?branch=master)](https://travis-ci.org/packetferret/juniper_build_config)

## Overview

`juniper_build_config` is an easier way to build complete Juniper configurations.

This collection is a based on the idea of using Jinja2 templating engine to build out a full Juniper device, and will expect a specific formatting of `host_vars` and `group_vars` variables. You may find working examples of these within the following project *[Ansible-Campus-Collapsed-Core](https://github.com/packetferret/Ansible-Campus-Collapsed-Core)*.

## Installation and Usage

### Installing the Collection from Ansible Galaxy

Before using the `juniper_build_config` collection, you need to install the collection with the `ansible-galaxy` CLI:
ansible-galaxy collection publish
    ansible-galaxy collection install juniper_build_config

You can also include it in a `requirements.yml` file and install it via `ansible-galaxy collection install -r requirements.yml` using the format:

```yaml
collections:
- name: juniper_build_config
```

## How to use this project

Merely import the roles into your playbook to build a specific (or set of specific) Juniper configuration stanzas.

>1. build files to host the various stanzas of a Juniper configuration
>2. assemble all stanza files into a full device configuration

### Roles used within this collection

Here is an up-to-date list of the roles supported within this collection today:

  - junos_config/build_directories
  - junos_config/access
  - junos_config/apply_groups
  - junos_config/chassis
  - junos_config/event_options
  - junos_config/class_of_service
  - junos_config/firewall
  - junos_config/forwarding_options
  - junos_config/groups
  - junos_config/interfaces
  - junos_config/poe
  - junos_config/policy_options
  - junos_config/protocols
  - junos_config/routing_instances
  - junos_config/routing_options
  - junos_config/security
  - junos_config/services
  - junos_config/snmp
  - junos_config/switch_options
  - junos_config/system
  - junos_config/version
  - junos_config/virtual_chassis
  - junos_config/vlans

## Development

Want to contribute? Great!

Submit a PR and let's work on this together :D
