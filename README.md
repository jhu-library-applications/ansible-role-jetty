Ansible Role: Jetty
=========

Installs and configures the [Jetty web server](https://www.eclipse.org/jetty/)

TODO: configure better logging
TODO: configure contexts


Requirements
------------

Java - the current version of Jetty (9.4) requires Java Virtual Machine (JVM) version 1.8 or higher. The requirements for older versions can be found [here](https://www.eclipse.org/jetty/documentation/current/what-jetty-version.html)


Role Variables
--------------

    java_version:             1.8
    jetty_version_major:      9
    jetty_version_minor:      4
    jetty_version_patch:      6
    jetty_version_build:      "v20170531"
    jetty_version:            "{{ jetty_version_major }}.{{ jetty_version_minor }}.{{ jetty_version_patch }}.{{ jetty_version_build }}"
    jetty_download_dir:       "{{ ansible_env.HOME}}"
    jetty_install_dir:        "/usr/local"
    jetty_dir:                "jetty-distribution-{{ jetty_version }}"
    jetty_download_file:      "{{ jetty_dir }}.tar.gz"
    jetty_url:                "http://central.maven.org/maven2/org/eclipse/jetty/jetty-distribution/{{ jetty_version }}/{{ jetty_download_file }}"
    jetty_checksum_algorithm: "sha1"
    jetty_checksum_url:       "{{ jetty_url }}.{{ jetty_checksum_algorithm }}"
    jetty_user:               "jetty"
    jetty_group:              "{{ jetty_user }}"
    jetty_port:               8080
    jetty_home:               "{{ jetty_install_dir }}/jetty"
    jetty_base:               "/opt/jetty"
    jetty_modules:            "http,deploy,console-capture,logging-jetty"
    jetty_debugging:          "{{ debugging | default(false) }}"
    jetty_test:               true
    java_opts:                "-Xms512m
                               -Xmx512m"


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
