ansible-role-users
=========

This role helps to manage user accounts. It will add and remove user accounts and manage group membership as well as sudo rights.

Requirements
------------

This role requires Ansible 1.4 or higher, and platform requirements are listed in the metadata file.

Role Variables
--------------

    ---
    users:
      testuser1:
        name: Test User1
        uid: 1001
        password: $1$b6BVxWF5$fMapNlhZ/aiPa/VzbARXI.
        sshkey: ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAxcNZk1CYAx52RrOOeWTJMplUCTNcAlnvt14STfpUdzAiuBy/a6axgY6AC9nh9C5mz6js8DmCjuv74u98huwrj3D3xCvNoG9BiBXxKDSBW5VHWbbpERz3AcM2lRK9KnP7qDK670Hln5NG5fsC2siMEm50EueZQP2YiWd+qNp6dvQI3KCMD97skX2zwc5+dZct5d3UywqJv17Pv4DUNpDmFlXiNHg3NiCpOcnr9JU2Hn5uHL30zjIeeWNeYtbv/+FmVOn4RgoHZzjhXyTrWRBEEkuPWoq75BkopShSnqDyJGycnMtUxNNdPB6Tyib5xNlxS81XlDR2kXVZZXpS8aojZQ== user@host
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

BSD

Author Information
------------------

Dan Levack <dan@levack.net>
