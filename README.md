Ansible Role: Jetty
=========

Installs and configures the [Jetty web server](https://www.eclipse.org/jetty/)


WIP Notice
----------

TODO: configure better logging
TODO: configure contexts


Requirements
------------

Java - the current version of Jetty (9.4) requires Java Virtual Machine (JVM) version 1.8 or higher. The requirements for older versions can be found [here](https://www.eclipse.org/jetty/documentation/current/what-jetty-version.html)


Role Variables
--------------

TBD


Dependencies
------------

Any role (or other method) that will provide a compatible version of Java.


Example Playbook
----------------

    - hosts: build
      roles:
         - { role: java }
         - { role: jetty }


License
-------

CC0


Author Information
------------------

Drew Heles
