# Eltex Ansible Project

_I plan to improve this project in the future._

## Common plan for improvement

- [ ] Fork the Ansible cisco.ios collection
- [ ] Create a list of modules that can be adapted for Eltex
- [ ] Define the order of the most important modules
- [ ] Implement the modules in this order
- [ ] Identify useful Ansible roles for device configuration
- [ ] Create the Ansible roles
- [ ] Prepare Ansible playbooks

Ansible Cisco IOS Collection: https://github.com/ansible-collections/cisco.ios

## Old description

Playbooks for automating routine administration tasks of Eltex switches.
(mes2100, mes2300, mes3300, mes3500, mes5300 series.)

Modules ios_command and ios_config are suitable (almost) for work with Eltex switches. I made two changes to the modules:

/usr/lib/python3/dist-packages/ansible_collections/cisco/ios/plugins/cliconf/ios.py
self.send_command("configure terminal") // "configure terminal" -> "configure"

/usr/lib/python3/dist-packages/ansible_collections/cisco/ios/plugins/terminal/ios.py
self._exec_cli_command(b"terminal lenght 0") // "terminal lenght 0" -> "terminal datadump"

This made it possible to use modules for Eltex.

mes-upgrade.yml - playbook for downloading new firmware images;
mes-schedule.yml - playbook for restarting switches on a schedule;
*.textfsm - templates for parsing.
