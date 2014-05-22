Stouts.iptables
===============

[![Build Status](https://travis-ci.org/Stouts/Stouts.hostname.png)](https://travis-ci.org/Stouts/Stouts.hostname)

Ansible role which manage iptables rules

#### Variables

```yaml
iptables_enabled: yes                   # The role is enabled
iptables_rules: []                      # List of rules
```

#### Usage

Add `Stouts.iptables` to your roles and setup the variables in your playbook file.
Example:

```yaml

- hosts: all

  roles:
    - Stouts.iptables

  vars:
    iptables_rules:
      - P INPUT DROP
      - P OUTPUT ACCEPT
      - A INPUT --dport 80 -j ACCEPT
      - A INPUT --dport 22 -j ACCEPT
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.hostname/issues)!
