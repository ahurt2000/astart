Script to create Symfony2 local project
======================================

This work on **Ubuntu** systems.

- Automatically create virtual host
- Fill **hosts** file *if it needed*
- Create the project folder 
- Download, extract symfony
- ACL permissions to cache & logs

You need to have ACL installed and enabled. Check your fstab. If you have not installed ACL or do you set permissions on your own you can put **"WITHACL = false"** in the config file

The project has this files:

- template.site: just a template for your .site vhost files
- vhostcreate :  bash script that generate vhost files form the template.site file
- hostexist: bash script to check if some host exist in your /etc/hosts file
- putacl: bash script usefull to set the correct permiss in app/cache & app/logs
- createpj: the main script that made all
- README.md: this file

The "putacl" script assumes that the apache user is 'www-data', but you can edit it.


Install
-------

Just download and unzip "astart" project.

Config
------

Copy config.dst to config

```
mv config.dst config
```

Edit the  script and configure  this vars

```
USER:   your user
MYPRJ:  your projects folders i.e: /home/$USER/projects
EXT:    domain ej: local or loc 
SERVERIP: apache ip usually 127.0.0.1 for local
SF2VERSION: Symfony version to install i.e: 2.0.4
VENDORS: Symfony 2 + vendors. Leave it blank if you prefer not vendors (default)
WITHACL: option for check or not ACL in ubuntu
```

*You probably don't need to change the default config*

USE 
---

You want to create a new project "blog". 

```
./astart/createpj blog
```

The script will ask you about yout root pass for 'sudo' operations.
After that you will have a blog folder with symfony and a vhost called blog.local


You can use these other scripts separately
------------------------------------------

*generate vhost files*

```
./astart/vhostcreate projectname super_domain projects_folder 

i.e: ./astart/vhostcreate blog local /home/myuser/myprojectsfolder
```

*putacl*  

from your project folder

```
sudo ../astart/putacl myuser  or sudo ../astart/putacl myuser myprojectfolder 
```

