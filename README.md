```
root@centos8s system]# tail -f /var/log/messages
Dec 27 13:50:10 centos8s systemd[1]: Starting system activity accounting tool...
Dec 27 13:50:10 centos8s systemd[1]: sysstat-collect.service: Succeeded.
Dec 27 13:50:10 centos8s systemd[1]: Started system activity accounting tool.
Dec 27 13:55:08 centos8s systemd[1]: Reloading.
Dec 27 13:59:12 centos8s vagrant[2779]: Wed Dec 27 13:59:12 UTC 2023: I found word, Master!
Dec 27 14:00:02 centos8s systemd[1]: Started Update a database for mlocate.
Dec 27 14:00:02 centos8s systemd[1]: Starting system activity accounting tool...
Dec 27 14:00:02 centos8s systemd[1]: sysstat-collect.service: Succeeded.
Dec 27 14:00:02 centos8s systemd[1]: Started system activity accounting tool.
Dec 27 14:00:02 centos8s systemd[1]: mlocate-updatedb.service: Succeeded.
=================================================================================
[root@centos8s system]# vi /etc/sysconfig/spawn-fcgi
[root@centos8s system]# vi /etc/systemd/system/spawn-fcgi.service
[root@centos8s system]# systemctl start spawn-fcgi
[root@centos8s system]# systemctl status spawn-fcgi
● spawn-fcgi.service - Spawn-fcgi startup service by Otus
   Loaded: loaded (/etc/systemd/system/spawn-fcgi.service; disabled; vendor preset: disabled)
   Active: active (running) since Wed 2023-12-27 14:14:14 UTC; 8s ago
 Main PID: 28110 (php-cgi)
    Tasks: 33 (limit: 11145)
   Memory: 18.8M
   CGroup: /system.slice/spawn-fcgi.service
           ├─28110 /usr/bin/php-cgi
           ├─28111 /usr/bin/php-cgi
           ├─28112 /usr/bin/php-cgi
           ├─28113 /usr/bin/php-cgi
           ├─28114 /usr/bin/php-cgi
           ├─28115 /usr/bin/php-cgi
           ├─28116 /usr/bin/php-cgi
           ├─28117 /usr/bin/php-cgi
           ├─28118 /usr/bin/php-cgi
           ├─28119 /usr/bin/php-cgi
           ├─28120 /usr/bin/php-cgi
           ├─28121 /usr/bin/php-cgi
           ├─28122 /usr/bin/php-cgi
           ├─28123 /usr/bin/php-cgi
           ├─28124 /usr/bin/php-cgi
           ├─28125 /usr/bin/php-cgi
           ├─28126 /usr/bin/php-cgi
           ├─28127 /usr/bin/php-cgi
           ├─28128 /usr/bin/php-cgi
           ├─28129 /usr/bin/php-cgi
           ├─28130 /usr/bin/php-cgi
           ├─28131 /usr/bin/php-cgi
           ├─28132 /usr/bin/php-cgi
           ├─28133 /usr/bin/php-cgi
           ├─28134 /usr/bin/php-cgi
           ├─28135 /usr/bin/php-cgi
           ├─28136 /usr/bin/php-cgi
           ├─28137 /usr/bin/php-cgi
           ├─28138 /usr/bin/php-cgi
           ├─28139 /usr/bin/php-cgi
           ├─28140 /usr/bin/php-cgi
           ├─28141 /usr/bin/php-cgi
           └─28142 /usr/bin/php-cgi
===================================================================================
Dec 27 14:14:14 centos8s.localdomain systemd[1]: Started Spawn-fcgi startup service by Otus.
[root@centos8s conf]# ss -tnulp | grep httpd
tcp   LISTEN 0      511          0.0.0.0:8080      0.0.0.0:*    users:(("httpd",pid=28990,fd=3),("httpd",pid=28989,fd=3),("httpd",pid=28988,fd=3),("httpd",pid=28986,fd=3))
tcp   LISTEN 0      511          0.0.0.0:80        0.0.0.0:*    users:(("httpd",pid=28604,fd=3),("httpd",pid=28603,fd=3),("httpd",pid=28602,fd=3),("httpd",pid=28600,fd=3))
[root@centos8s conf]# 
```
