# Ansible-playbook-wordpress-LAMP

[![Build](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

---

## Description 



----
## Pre-Requests
- Need to install Ansible on Master node to run
-----

## Includes

- Mariadb
- php
- wordpress
- Apache

### Ansible installation 

```sh
sudo amazon-linux-extras install ansible2 -y

ansible --version
ansible 2.9.23
  config file = /etc/ansible/ansible.cfg
  configured module search path = [u'/home/ec2-user/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python2.7/site-packages/ansible
  executable location = /usr/bin/ansible
  python version = 2.7.18 (default, Jun 10 2021, 00:11:02) [GCC 7.3.1 20180712 (Red Hat 7.3.1-13)]
```


### Behind the code





```

[ec2-user@ip-172-31-32-109 ~]$ ansible-playbook -i hosts main.yml --syntax-check

playbook: main.yml
[ec2-user@ip-172-31-32-109 ~]$ ansible-playbook -i hosts main.yml

PLAY [Installing WordPress with LAMP Stack on Amazon Linux] ************************************************************
TASK [Gathering Facts] *************************************************************************************************[WARNING]: Platform linux on host 172.31.34.80 is using the discovered Python interpreter at /usr/bin/python, but
future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
ok: [172.31.34.80]

TASK [APACHE WEBSERVER INSTALLATION] ***********************************************************************************
changed: [172.31.34.80]

TASK [Installing PHP] **************************************************************************************************
changed: [172.31.34.80]

TASK [Adding Virtualhost form local to destination] ********************************************************************
changed: [172.31.34.80]

TASK [Creating Documentroot for jomygeorge.xyz] ************************************************************************
changed: [172.31.34.80]

TASK [Start & Enable Apache webserver] *********************************************************************************
changed: [172.31.34.80]

TASK [Installing and setting up the Mariadb-server] ********************************************************************
changed: [172.31.34.80]

TASK [Restarting & Enabling Mariadb] ***********************************************************************************
changed: [172.31.34.80]

TASK [Setup Root password for root user] *******************************************************************************
[WARNING]: Module did not set no_log for update_password
changed: [172.31.34.80]

TASK [Create and passing the file from local to destination /root/.my.cnf] *********************************************
changed: [172.31.34.80]

TASK [Removing mariadb anonymous users] ********************************************************************************
changed: [172.31.34.80]

TASK [Remove test database from mariadb] *******************************************************************************
ok: [172.31.34.80]

TASK [Creating the wordpress database] *********************************************************************************
changed: [172.31.34.80]

TASK [Creating Wordpress user] *****************************************************************************************
changed: [172.31.34.80]

TASK [Downloading the Wordpress zip file on remote meachine] ***********************************************************
changed: [172.31.34.80]

TASK [Extracting Wordpress file on remote meachine] ********************************************************************
changed: [172.31.34.80]

TASK [Moving Wordpress extracted files to website Document root] *******************************************************
changed: [172.31.34.80]

TASK [Creating wp-config.php and pass to remote meachine] **************************************************************
changed: [172.31.34.80]

TASK [Post installation restart for the httpd and mariadb service] *****************************************************
changed: [172.31.34.80] => (item=httpd)
changed: [172.31.34.80] => (item=mariadb)

PLAY RECAP *************************************************************************************************************
172.31.34.80               : ok=19   changed=17   unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
