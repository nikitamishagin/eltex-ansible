# eltex-ansible
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
