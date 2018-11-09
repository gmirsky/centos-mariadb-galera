CentOS-MariaDB-Galera
=====================

Playbook to configure a CentOS 7 based MariaDB Galera cluster and load it up with the MySQL employee test database for training purposes.

WORK IN PROGRESS DO NOT USE


Requirements
------------

See dependencies section for the sample database that must be downloaded from GitHub.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

galera_cluster_name: Name of the MariaDB Galera Cluster.
galera_cluster_user: Cluster User ID.
galera_clustercheck_user: Cluster User ID used to check the health of the cluster.





Ansible Vault Password is ===>  C0mpl1c@t3

Please create your own vault file and use a more secure password.

The file user_passwords_original.yml contains the original file unencrypted. Please change the passwords from 'dbpass' to something more secure.

Use the following command to create your encrypted file.

ansible-vault create user_passwords.yml

Provide passwords when prompted.

Once in vi editor mode, hit the 'i' key to go into insert mode. Paste the contents of user_passwords_original.yml in your edited file. Remember! Change the passwords to something more secure!

Hit escape to exit insert mode, then type ':wq' (without the quotes) to save the file.

View your file and make sure it is encrypted.

Verify you did things correctly by using the following command to see if you can unencrypt your file.

ansible-vault view  user_passwords.yml --ask-vault-pass

Supply the password you used. You should be able to view your file unencrypted.


Dependencies
------------
This playbook utilizes the MySQL Employees sample database. The database contains about 300,000 employee records with 2.8 million salary entries. The export data is 167 MB, which is not huge, but large enough to be non-trivial and also the reason it is not included with this repository.

The database is available here:

https://github.com/datacharmer/test_db

Download from GitHub as a zip file and place the test_db-master.zip file in the files directory.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

Written by Gregory Mirsky.
