# cesnet.wazuh
Ansible role for installing Wazuh agent.

## Variables

* **wazuh_manager** - DNS domain name of Wazuh server, it is used as the value of the WAZUH_MANAGER environment variable
* **wazuh_registration_password** - password, it is used as the value of the WAZUH_REGISTRATION_PASSWORD environment variable
* **wazuh_agent_group** - comma separated list of groups, it is used as the value of the WAZUH_AGENT_GROUP environment variable
* **wazuh_agent_name** - agent namem it is used as the value of the WAZUH_AGENT_NAME environment variable, default is inventory_hostname

## Examples

Example of using this role in an Ansible playbook:
```yaml
- hosts: cloud1.perun-aai.org
  remote_user: root
  vars:
    wazuh_manager: "gvm-wazuh1.cesnet.cz"
    wazuh_agent_group: "712"
    wazuh_registration_password: '*****'
  tasks:
    - name: "install wazuh agent"
      import_role:
        name: cesnet.wazuh
```
