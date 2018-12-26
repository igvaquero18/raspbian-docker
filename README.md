Raspbian Docker
=========

This role installs Docker on Raspbian operating systems following the official procedure at [Get Docker CE for Debian](https://docs.docker.com/install/linux/docker-ce/debian/#upgrade-docker-ce-1). 

Requirements
------------

Raspbian 9 (stretch) or later. It hasn't been tested with older versions, but that doesn't necessarily mean it can't work. Indeed, it should work with some older Raspbian versions.

Role Variables
--------------

This role has only two variables:
- **docker_version**: Optional. This is the Docker version you wish to install. If it's not specified, the latest version will be installed.
- **docker_users**: Optional. A list of users that are to be added to the `docker` group in order for them to be able to run docker commands without sudo privileges. Please check the [Docker Daemon attack surface](https://docs.docker.com/engine/security/security/#docker-daemon-attack-surface) documentation for understanding the risks of adding users to the `docker` group.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: docker-servers
      roles:
         - { role: igvaquero18.raspbian-docker, docker_users: [ignacio] }

License
-------

BSD

Author Information
------------------

Ignacio Vaquero Guisasola.
DevOps Engineer at ING Spain.
[ivaqueroguisasola@gmail.com](mailto:ivaqueroguisasola@gmail.com).
