Enable https using certbot
=========

enable https.

* Install mod_ssl
* Install epel_release
* Install certbot
* Setup ssl.conf
* Add cron task to update certificate file
* Open 443 port

Requirements
------------

* httpd installed and worked.

Role Variables
--------------

default variables
```
webroot_dir: /var/www/html
ssl_conf_path: /etc/httpd/conf.d/ssl.conf
# host_name is tossed by playbook
certificate_file_dir: /etc/letsencrypt/live/{{ host_name }}
cron_log_path: /home/root/letsencrypt.log
```

should be passed variables
```
host_name
mail_address
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
         - { role: tsyki.enable-https, host_name: www.example.com, mail_address: example@example.com}

License
-------

BSD

Author Information
------------------

Toshiyuki Imaizumi
