Role Name
========

Ansible Role to Install Riemann. Riemann aggregates events from your servers and applications with a powerful stream processing language. See http://riemann.io

Requirements
------------

Riemann requires Java. EPEL must be present on RedHat OS systems. 

The role will take care of this dependencies, however you can disable this behavior with `--skip-tags=deps`.

Role Variables
--------------

Variables that can be passed to this role:

`riemann_deb: ""` The url of Riemann package

`riemann_rpm: ""` The url of Riemann package

`riemann_open_jdk: "java-1.7.0-openjdk"` The version of OpenJDK (RH)

`riemann_open_jdk: "openjdk-7-jre"` The version of OpenJDK (Debian)

`includedir: "~/custom_templates/"` A directory from where to load a custom template. If not defined the default templates/ from the role is used.

`riemann_user: ""` The owner of Riemann configuration file

Variables with fixed values:

`epel_url: ""` The url of EPEL package

`riemann_conf: ""` The configuration file for Riemann

`ansible_eth0.ipv4.address` The interface under which Riemann should listen

Dependencies
------------

None

Example Playbook
-------------------------

    - hosts: riemannServers
      roles:
         - { role: valentinogagliardi.riemann,
                   riemann_open_jdk: "openjdk-7-jre",
                   includedir: "",
                   tags: ["riemann"] }

License
-------

GNU General Public License Version 2

Author Information
------------------

Valentino Gagliardi - valentino.g@servermanaged.it
