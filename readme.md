# Ansible Role: LibreNMS

An Ansible Role that installs LibreNMS on Ubuntu server.

## Requirements

Ubuntu Server 18.04.4 LTS or greater.

## Role Variables
#### Available variables are listed below, along with default values (see `defaults/main.yml`):

    snmp_location
    snmp_contact
    snmp_v2_community

Values for the snmpd.conf file. V2 community is used for access to the ubuntu server.

    librenms_required_packages

List of all packages required to be installed via APT for libreNMS. (see https://docs.librenms.org/Installation)


## Dependencies

    - none
## Example Playbook

    - hosts: all
      become: yes
      become_method: sudo
      roles:
        - librenms