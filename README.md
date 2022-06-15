# RHEL & SAP Automation

[![License: GPLv2](https://img.shields.io/badge/license-GPLv2-brightgreen.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
[![License: GPLv3](https://img.shields.io/badge/license-GPLv3-brightgreen.svg)](https://www.gnu.org/licenses/gpl-3.0)

Ansible playbooks to automate RHEL & SAP setup.

## Playbooks

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

## Quick Example

To prepare and verify RHEL, setup SAP HANA, setup SAP HANA HSR, and
setup Pacemaker for SAP HANA, run the playbooks as follows. This example
expects that basics like SSH keys and sudo to be configured and SAP HANA
and SAP Host Agent installation files to be found from the expected
locations.

Each playbook contains installation specific settings that should be
adjusted as needed. Since some of the playbooks may reboot nodes the
playbook are executed from a separate Control Node.

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

## Ansible Role Description

The Ansible roles for SAP supported by Red Hat are included in the
_rhel-system-roles-sap_ RPM package.

See the following RHKB articles for support status of the included roles:

* [https://access.redhat.com/articles/4488731](https://access.redhat.com/articles/4488731)
* [https://access.redhat.com/articles/6857351](https://access.redhat.com/articles/6857351)

The currently unsupported (as of 2022-06) SAP HANA HSR role is from the
joint IBM/Red Hat/SAP/SUSE upstream repository:

* [https://github.com/sap-linuxlab/community.sap_install](https://github.com/sap-linuxlab/community.sap_install)

The SAP HANA Pacemaker role included in this repository is based on the
upstream _dev_ branch current (as of 2022-06) under active developement:

* [https://github.com/mmoster/community.sap_install/tree/dev](https://github.com/mmoster/community.sap_install/tree/dev)

The older, now deprecated SAP RHEL roles can be found from:

* [https://github.com/redhat-sap](https://github.com/redhat-sap)

The Red Hat Knowledge Base article explaining the details of RHEL & SAP
HANA setup is at:

* [https://access.redhat.com/articles/3004101](https://access.redhat.com/articles/3004101)

The playbooks have been tested with the RHEL 8.4 E4S roles. Please be
prepared to update the playbooks and especially the variables used when
upgrading to newer versions.

## See Also

See also
[https://github.com/myllynen/rhel-ansible-roles](https://github.com/myllynen/rhel-ansible-roles).

## License

GPLv2+
