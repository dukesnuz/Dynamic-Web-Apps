## Setting up a local domain in order to use domain.loc when using MAMP

[Class Material](https://github.com/susanBuck/dwa15-fall2017/blob/master/01_Servers_and_Git/09_Local_domain.md)

My set up using MAMP on windows

1. Tell Apache to use the virtual hosts file - One time set up
Path c:   \MAMP\conf\apache\httpd-vhosts.conf
Virtual hosts Uncomment line Include conf/extra/httpd-vhosts.conf

2. Create a new host - For each Domain go to  c:/Windows/System32/drivers/etc/hosts - add to bottom  127.0.0.1 domain.loc
   (Do not use command line, open in explorer, notepad
   
3.  Virtual host entry - For eaxh domain go to c:  ```\mamp\bin\apache\conf\extra```
    nano httpd-vhosts.conf
    (Open in commmand line)

 Add
 
```
<VirtualHost *:80>
    ServerName domain.loc
    DocumentRoot c:/mamp/htdocs/newfolder
    <Directory c:/mamp/htdocs/newfolder>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
    </Directory>
</VirtualHost>
```
For localhost
```
<VirtualHost *:80>
    ServerName localhost
    DocumentRoot c:/MAMP/htdocs/
    <Directory c:/MAMP/htdocs/>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
    </Directory>
</VirtualHost>
```

[Debugging local server](https://github.com/susanBuck/dwa15-fall2017/blob/master/01_Servers_and_Git/02_Debugging_local_servers.md)
