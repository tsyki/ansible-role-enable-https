Enable https
=========

enable https.

* install mod_ssl
* copy private key and certificate file
* open 443 port

Requirements
------------

* httpd installed
* private key and certificate file is created

Role Variables
--------------

```
private_key_file_name: server.key
dest_private_key_dir: /etc/pki/tls/private
dest_private_key_path: "{{ dest_private_key_dir}}/{{ private_key_file_name }}"

certificate_file_name: server.crt
dest_certificate_dir: /etc/pki/tls/certs
dest_certificate_path: "{{ dest_certificate_dir}}/{{ certificate_file_name }}"

ssl_conf_path: /etc/httpd/conf.d/ssl.conf
```

Dependencies
------------

none

Example Playbook
----------------

Before run playbook, you need put the private key and certificate file under tsyki.enable-https/files.

    - hosts: servers
      become: yes
      roles:
         - { role: tsyki.enable-https }

License
-------

BSD

Author Information
------------------

Toshiyuki Imaizumi
