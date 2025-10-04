# Eltex Ansible Project

**PROJECT UNDER DEVELOPMENT**

🚀 Join the effort to build a dedicated Eltex Ansible collection!  

If you work with Eltex network devices and are familiar with Ansible/Python, I invite you to contribute. The plan is a
phased adaptation of modules from the cisco.ios collection for Eltex devices within the dedicated
`feature/ansible-collection` branch. Please propose and implement your Eltex-specific adaptations following the roadmap
below.

I’m happy to receive any suggestions, ideas, and support for creating this collection. Thank you!


## Common plan for improvement

- [x] Fork the Ansible cisco.ios collection
- [ ] Create a list of modules that can be adapted for Eltex
- [ ] Define the order of the most important modules
- [ ] Implement the modules in this order
- [ ] Identify useful Ansible roles for device configuration
- [ ] Create the Ansible roles
- [ ] Prepare Ansible playbooks

Ansible Cisco IOS Collection: https://github.com/ansible-collections/cisco.ios

## Progress of improvement

- The improvement plan has been drafted and added to the README.
- A brief section for contributors has been added.
- A new branch has been created to evolve the project into an Ansible collection. The branch is named
  `feature/ansible-collection`. It is currently a copy of the cisco.ios project. All development of the new collection
  is planned to take place in this branch (as if it were the new main).

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
