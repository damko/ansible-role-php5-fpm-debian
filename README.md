Ansible php5-fpm Debian
=====

This Ansible role installs and configures the php5-fpm for Nginx on a Debian system (wheezy).
Optionally it can install phpmyadmin (just the package without any particular configuration).

Requirements
------------

This role requires Ansible 1.4 or higher and the ansible role damko.nginx-debian just because in that role I set the variable {{nginx_user}} which is used also by this role.

Role Variables
--------------

You can see the variables that can be passed to this role by checking the file `defaults/main.yml`.


Examples
========

All options:

    - {
         role: damko.php5-fpm-debian,
             install_phpmyadmin: false,
             use_tcp_ip_connection: false,
             php5_host_ip: 127.0.0.1
             php5_tcp_ip_port: 9000
     }


1. Install php5-fpm configured to use unix socket connection. No phpmyadmin will be installed

    - role: damko.php5-fpm-debian

2. Install php5-fpm using tcp_ip connection on 127.0.0.1:9001:

    - {
         role: damko.php5-fpm-debian,
             use_tcp_ip_connection: true,
             php5_tcp_ip_port: 9001
     }


License
-------

BSD

Author Information
------------------

Damiano Venturin

