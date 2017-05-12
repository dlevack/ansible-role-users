ansible-role-users
=========

This role helps to manage user accounts. It will add and remove user accounts and manage group membership as well as sudo rights.

Requirements
------------

This role was developed and tested on Ansible 2.2.0 and higher. It may work on lower versions but that is currently untested.


Role Variables
--------------

    ---
    users:
      testuser1:
        name: Test User1
        uid: 1001
        password: $1$b6BVxWF5$fMapNlhZ/aiPa/VzbARXI.
        sshkey: ssh-rsa AAAAB3N.... user@host
        shell: /bin/bash
        groups: admins, developers

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

Deploy users to Database servers:

    - hosts: Database
      roles:
         - dlevack.users

Deploy users to Mail servers:

    - hosts: Mail
      roles:
         - dlevack.users

Deploy users to Database and Mail servers:

    - hosts: Database
      roles:
         - dlevack.users
    - hosts: Mail
      roles:
         - dlevack.users

Deploy users to all servers:

    - hosts: all
      roles:
         - dlevack.users


Dependencies
------------

None

License
-------

BSD-2-Clause

Author Information
------------------

Dan Levack <dan@levack.net>
