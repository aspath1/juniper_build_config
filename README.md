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

example:

```yml
### ---------------------------------------------------------------------------
### BUILD CONFIGURATION IN PIECES AND ASSEMBLE INTO SINGLE CONFIG FILE
### ---------------------------------------------------------------------------
- hosts: all
  connection: local
  any_errors_fatal: "{{ any_errors_fatal | default(true) }}"
  gather_facts: False
  roles:
    - { role: build_config_stanza/version }
    - { role: build_config_stanza/apply_groups }
    - { role: build_config_stanza/groups }
    - { role: build_config_stanza/system }
    - { role: build_config_stanza/event_options, when: "'switch' in device.role" }
    - { role: build_config_stanza/chassis }
    - { role: build_config_stanza/services, when: "'firewall' in device.role" }
    - { role: build_config_stanza/security, when: "'firewall' in device.role" }
    - { role: build_config_stanza/interfaces }
    - { role: build_config_stanza/snmp }
    - { role: build_config_stanza/forwarding_options }
    - { role: build_config_stanza/routing_instances }
    - { role: build_config_stanza/routing_options }
    - { role: build_config_stanza/protocols }
    - { role: build_config_stanza/policy_options }
    - { role: build_config_stanza/class_of_service }
    - { role: build_config_stanza/firewall }
    - { role: build_config_stanza/switch_options }
    - { role: build_config_stanza/poe }
    - { role: build_config_stanza/virtual_chassis, when: "'virtual_chassis' in device.role" }
    - { role: build_config_stanza/access }
    - { role: build_config_stanza/vlans }
    - { role: assemble_config }
```

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
  - junos_config/assemble_config

## Development

Want to contribute? Great!

Submit a PR and let's work on this together :D
