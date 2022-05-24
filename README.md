# RHEL SAP Automation

[![License: GPLv2](https://img.shields.io/badge/license-GPLv2-brightgreen.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
[![License: GPLv3](https://img.shields.io/badge/license-GPLv3-brightgreen.svg)](https://www.gnu.org/licenses/gpl-3.0)

Ansible playbooks to automate RHEL & SAP setup.

## Contents

* [sap_hana_rhel_prepare.yml](sap_hana_rhel_prepare.yml)
  * Prepare RHEL system for SAP HANA installation
* [sap_hana_rhel_verify.yml](sap_hana_rhel_verify.yml)
  * Verify RHEL system configuration for SAP HANA
* [sap_hana_setup.yml](sap_hana_setup.yml)
  * Setup SAP HANA
* [sap_hana_setup_hsr.yml](sap_hana_setup_hsr.yml)
  * Setup SAP HANA HSR
* [sap_hana_setup_pacemaker.yml](sap_hana_setup_pacemaker.yml)
  * Setup Pacemaker for SAP HANA
* [sap_host_agent_setup.yml](sap_host_agent_setup.yml)
  * Setup SAP Host Agent (optional)

## Example

To prepare and verify RHEL, setup SAP HANA, setup SAP HANA HSR, and
setup Pacemaker for SAP HANA, run the playbook as follows. This example
expects that basics like SSH keys and sudo have been configured and SAP
HANA and Host agent installation files will be found from the expected
locations.

```
ansible-playbook -i saphana1.example.com,saphana2.example.com \
  sap_hana_rhel_prepare.yml
ansible-playbook -i saphana1.example.com,saphana2.example.com \
  sap_hana_rhel_verify.yml
ansible-playbook -i saphana1.example.com,saphana2.example.com \
  sap_hana_setup.yml
ansible-playbook -i saphana1.example.com,saphana2.example.com \
  sap_hana_setup_hsr.yml
ansible-playbook -i saphana1.example.com,saphana2.example.com \
  sap_hana_setup_pacemaker.yml
ansible-playbook -i saphana1.example.com,saphana2.example.com \
  sap_hana_rhel_verify.yml
```

## See Also

See also
[https://github.com/myllynen/rhel-ansible-roles](https://github.com/myllynen/rhel-ansible-roles).

## License

GPLv2+
