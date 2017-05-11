ansible-role-users
=========

This role helps to manage user accounts. It will add and remove user accounts and manage group membership as well as sudo rights.

Requirements
------------

This role requires Ansible 1.4 or higher, and platform requirements are listed in the metadata file.

Role Variables
--------------

Dependencies
------------

None

Example Host file
-----------------

    [Database]
    mysqlserver
    
    [Mail]
    mailserver
    
    [Web]
    webserver

Example Playbook
----------------

    - hosts: Database
      roles:
         - dlevack.users

License
-------

BSD

Author Information
------------------

Dan Levack <dan@levack.net>
