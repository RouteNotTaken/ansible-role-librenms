# Ansible Role: LibreNMS

An Ansible Role that installs LibreNMS on Ubuntu server.

## Requirements

Ubuntu Server 18.04.4 LTS or greater.

## Role Variables
#### Available variables are listed below, along with default values (see `defaults/main.yml`):

    db_host (required)
    db_user
    db_port
    db_pass (required)
Values for the external database server hosting the librenms table. User and port defined in defaults, host and pass required.

    memcached_host
    rrdcached_host
Hostname or IP adddress of the server running memcached and rrdached. Uses default ports.

    snmp_location
    snmp_contact
    snmp_v2_community
Values for the snmpd.conf file. V2 community is used for access to the ubuntu server.

    librenms_required_packages
List of all packages required to be installed via APT for libreNMS. (see https://docs.librenms.org/Installation)


## Dependencies
    - LibreNMS webserver
    - Server running memcahced and rrdcached
    - LibreNMS database, rights granted to every polling server

## Example Playbook

    - hosts: all
      become: yes
      become_method: sudo

      vars:
        db_host: 192.1.1.10
        db_pass: password
        memcached_host: 192.1.1.10
        rrdcached_host: 192.1.1.10
      roles:
        - librenms
