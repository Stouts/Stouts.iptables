Stouts.iptables
===============

[![Build Status](https://travis-ci.org/Stouts/Stouts.hostname.png)](https://travis-ci.org/Stouts/Stouts.hostname)

Ansible role which manage iptables

* Install iptables
* Add rules
* Autosave rules when system is rebooted

#### Variables

```yaml
iptables_enabled: yes                   # The role is enabled
iptables_autosave: yes                  # Save and load iptables rules when system is rebooted
iptables_allow_lo: yes                  # Allow all on local interface
iptables_rule_path: /etc/iptables.rules # Path to rule file
iptables_rules: []                      # List of rules
                                        # Ex. iptables_rules:
                                        #     - { protocol: tcp, port:80 }
                                        #     - { protocol: tcp, port:22 }
iptables_raw_rules: []                  # List of raw rules
                                        # Ex. iptables_raw_rules:
                                        #     - -A INPUT -i eth0 -p tcp -m tcp --dport 22 -j ACCEPT
                                        #     - -A INPUT -i eth0 -p tcp -m tcp --dport 80 -j ACCEPT
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
    - { protocol: tcp, port: 80 }
    - { protocol: tcp, port: 22 }
    - { protocol: tcp, port: 443 }
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.hostname/issues)!
