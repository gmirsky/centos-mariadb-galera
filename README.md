# CentOS-MariaDB-Galera
=====================

Playbook to configure a CentOS 7 based MariaDB Galera cluster for training purposes. This playbook will load up the servers in the MariaDB Galera cluster with the MySQL employee test database.

## Requirements
------------

See dependencies section for the sample database that must be downloaded from GitHub.

## Role Variables
--------------

galera_cluster_name: Name of the MariaDB Galera Cluster.
galera_cluster_user: Cluster User ID.
galera_clustercheck_user: Cluster User ID used to check the health of the cluster.


## Encrypt user_passwords.yml
-------------------------

Please change the passwords in the user_passwords.yml file, then encrypt your user_passwords.yml using the Ansible vault utility. Instructions below.

Use the following command to create your encrypted file.

    ansible-vault create user_passwords.yml

Provide passwords when prompted by the Ansible vault utility.

The Ansible vault utility will place you into a vi editor dialog. Once in vi editor mode, hit the 'i' key to go into insert mode. Paste the contents of user_passwords_original.yml in your edited file. Remember! Change the passwords to something more secure!

Hit escape to exit insert mode, then type ':wq' (without the quotes) to save the file.

Now, view your file and make sure it is encrypted. Verify you did things correctly by using the following command to see if you can un-encrypt your file.

    ansible-vault view  user_passwords.yml --ask-vault-pass

Supply the password you used. You should be able to view your file unencrypted.


## Dependencies
------------
This playbook utilizes the MySQL Employees sample database. The database contains about 300,000 employee records with 2.8 million salary entries. The export data is 167 MB, which is not huge, but large enough to be non-trivial and also the reason it is not included with this repository.

The database is available here:

    https://github.com/datacharmer/test_db

Download from GitHub as a zip file and place the test_db-master.zip file in the files directory.

## Executing the playbook
---------------------

Below is a sample bash script that you can use to run the play book. Remember to update the items in the inventory file to reflect your environment.

    #!/bin/bash
    export ANSIBLE_HOST_KEY_CHECKING=False
    ansible-playbook --inventory-file=../tests/inventory --user myuserid  ../tasks/main.yml

License
-------

BSD

Author Information
------------------

Written by Gregory Mirsky.
