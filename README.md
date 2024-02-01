Role Name
=========

Nagios NRPE for checking running docker containers

Galaxy : yes

Requirements
------------

NRPE is already installed

Role Variables
--------------

vars:

- *containers*: list of docker containers that should run on target host

e.g. This can be the host_var for host *docker01*

    containers:
    - hello_world
    - pihole
    - guacamole

Dependencies
------------

*role_nrpe* to install/configure NRPE

Example Playbook
----------------

the var *containers* is optional and can be defined as host_var.  
Note that the role is only useful if this var is defined.  
Else there will be nothing to check.  
*arikkert.nrpe_check_docker* will install *arikkert.role_nrpe* as dependency

    - hosts: docker01
      roles:
        - role: arikkert.nrpe_check_docker
          when: containers is defined

Example of a script that uses this role : https://github.com/arikkert/ansible-dockerhost

License
-------

BSD

Author Information
------------------

    ARK-ICT
    Andre Rikkert de Koe - ICT
