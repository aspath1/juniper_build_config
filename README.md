# juniper_build_config

[![N|Solid](https://upload.wikimedia.org/wikipedia/commons/3/31/Juniper_Networks_logo.svg)](https://www.juniper.net/documentation/solutions/en_US/campus)

[![Build Status](https://travis-ci.org/packetferret/Ansible-juniper_build_config.svg?branch=master)](https://travis-ci.org/packetferret/juniper_build_config)

## Overview

`juniper_build_config` is an easier way to build complete Juniper configurations.

This collection is a based on the idea of using Jinja2 templating engine to build out a full Juniper device, and will expect a specific formatting of `host_vars` and `group_vars` variables. You may find working examples of these within the following project *[Ansible-Campus-Collapsed-Core](https://github.com/packetferret/Ansible-Campus-Collapsed-Core)*.

## Installation and Usage

### Installing the Collection from Ansible Galaxy

Before using the `juniper_build_config` collection, you need to install the collection with the `ansible-galaxy` CLI:

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

  - build_directories
  - junos_access
  - junos_apply_groups
  - junos_chassis
  - junos_event_options
  - junos_class_of_service
  - junos_firewall
  - junos_forwarding_options
  - junos_groups
  - junos_interfaces
  - junos_poe
  - junos_policy_options
  - junos_protocols
  - junos_routing_instances
  - junos_routing_options
  - junos_security
  - junos_services
  - junos_snmp
  - junos_switch_options
  - junos_system
  - junos_version
  - junos_virtual_chassis
  - junos_vlans

## Development

Want to contribute? Great!

Submit a PR and let's work on this together :D
