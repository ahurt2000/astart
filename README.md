Sript to create Symfony2 local project
======================================

This work on **Ubuntu** systems 

- Automatically create virtual host
- Fill **hosts** file *if it needed*
- Create the project folder 
- Download, extract symfony
- ACL permissions to cache & logs

You need to have ACL installed and enabled. Check your fstab.
The "putacl" script assumes that the apache user is 'www-data', but you can edit it.


Install
-------

Just download and unzip "astart" project.

Config
------

Edit the createpj script and configure  this vars

```
USER:   your user
MYPRJ:  your projects folders ej /home/$USER/projects
EXT:    domain ej: local or loc 
SERVERIP: apache ip usually 127.0.0.1 for local
SF2VERSION: Symfony version to install ej: 2.0.4
```

*You probably just need to change the user*

USE 
---

You want to create a new project "blog". 

```
sudo ./astart/createpj blog
```

After that you will have a blog folder with symfony and a vhost called blog.local

