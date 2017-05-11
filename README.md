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
        password: $1$4k.ggzUl$jPToyRQXJguRntgRN/Z6H1
        sshkey: ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA2LTRhIlEQuibfGA2KVHaLoN6AKZcx38Gvw415Ge14YD+gFHogwc4a8eO4Gpg4eSB5WyHrD6Lr/b1GbgQKfwIIewdjvfxbm6CH/oJoWZ2VnXABg+nuLZRICt4mV/Gz9ZvbLRyFsDCSiNtqPUa5LQyGJeIJ3I0/dEv3E7V5IU6rJhUN6wXLmbZtUlpjzje99Tjab17m4ZWkgveSr89euhmZ9auoLjokG8ITqizMbk3pqR3ZvCVsquCdb//Ke5qxvVUaiicpTeFCjpYdfsoDeCVhoFm5mx2j9YhNng49/oPBL46eJBkY5xuj0UGTxqnc+EzTKi/kqdc/4qakcM6hxPzqQ== user@host
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
