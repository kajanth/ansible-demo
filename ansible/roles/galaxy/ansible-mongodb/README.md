ansible-mongodb
=========

Minimal role to deploy a single MongoDB node with one authenticate user.

[MongoDB](http://www.mongodb.org/)

* Install and configure  MongoDB 3.2 on Ubuntu 14.04 and Centos 6.6;
* Provide hanlers for restart and reload;

Requirements
------------

N/A


Role Variables
--------------
```yaml
#This user is for the mongo lockdown on the admin db.
mongodb_admin_user:   mongoadmin
mongodb_admin_pass:   <choose_a_strong_password>
mongodb_admin_host:   localhost
mongodb_admin_host_port: 27017
#This user is for a regular db.
mongodb_database:   mydb
mongodb_user:       mydb_user
mongodb_pass:       <choose_a_strong_password>
mongodb_user_state: present
mongodb_user_role:  dbOwner
```

Dependencies
------------

N/A


Example Playbook
----------------

Add `Stouts.mongodb` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
  - p0bailey.mongodb

  vars:
      mongodb_admin_user:   mongoadmin
      mongodb_admin_pass:   <choose_a_strong_password>
      mongodb_admin_host:   localhost
      mongodb_admin_host_port: 27017
      #This user is for a regular db.
      mongodb_database:   mydb
      mongodb_user:       mydb_user
      mongodb_pass:       <choose_a_strong_password>
      mongodb_user_state: present
      mongodb_user_role:  dbOwner
```

License
-------

BSD

Author Information
------------------

Phillip Bailey <phillip@bailey.st>
