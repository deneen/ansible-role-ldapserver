Role Name
=========

Builds an OpenLDAP server. Currently only tested on RHEL 7.

Requirements
------------

Uses standard Ansible modules.

Role Variables
--------------

- ldap_top - top dc for the Domain, used to build the domain and in the base.ldif.j2 template to build the base db
- ldap_base - base of the LDAP Domain
- ldap_root - account used as the root/admin for the LDAP db
- cert_dest_path - remote directory where certs will be copied
- ca_src_path - local directory where the CA cert is stored
- server_src_path - local directory where the server cert and key is stored
- server_cert - full path for the server cert (remote) - default is {{ cert_dest_path }}/{{ ansible_nodename }}.cert
- server_key - full path for the server key (remote) - default is {{ cert_dest_path }}/{{ ansible_nodename }}.key
- ca_cert - full path for the CA cert (remote) - default is {{ cert_dest_path }}/cacert.pem
- ca_source_cert - full path where local copy of the CA cert is stored - default is {{ ca_src_path }}/cacert.pem
- server_source_cert - full path for the server cert (local) - default is {{ server_src_path }}/{{ ansible_nodename }}.cert
- server_source_key - full path for the server key (local) - default is {{ server_src_path }}/{{ ansible_nodename }}.key
- ldap_root_passwd: root/admin password
- schema_adds: list of ldif files to expand the schema for the LDAP db

DB_CONFIG setting -
- db_lock_expire - boolean, if true, enables db_lock_expire setting
- db_log_autoremove - boolean, if true, enables auto-remove of transaction logs 
- db_lg_max - sets transaction log max
- db_cachesize - sets cachesize settings
- db_checkpoint - sets checkpoint settins


License
-------
BSD

