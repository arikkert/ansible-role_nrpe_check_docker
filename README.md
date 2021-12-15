Role Name
=========

Nagios NRPE for checking running docker containers

Requirements
------------

NRPE is already installed

Role Variables
--------------

vars:

- *containers*: list of docker containers that should run on target host

e.g. This can be the host_var for host docker01

    containers:
    - hello_world
    - pihole
    - guacamole

Dependencies
------------

*role_nrpe* to install/configure NRPE

Example Playbook
----------------

the var containers is optional and can be defined as host_var.
Note that the role is only useful as this var is defined.
Else there will be nothing to check.

    - hosts: docker01
      roles:
        - role: role_nrpe
          when: containers is defined
        - role: role_nrpe_check_podman
          when: containers is defined

License
-------

BSD

Author Information
------------------

    ARK-ICT
    Andre Rikkert de Koe - ICT
