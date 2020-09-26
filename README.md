<p align="center">
<img src="https://i.ytimg.com/vi/uuutAIRFSec/maxresdefault.jpg" width="100%">
</p>

# This project contains Nginx with PHP and WinSW.NET2 #
- Nginx 1.18.0 Stable version - [https://nginx.org/en/download.html]
- Php7.4.10 - [https://windows.php.net/download/]
- WinSW v2.10.2 - [https://github.com/winsw/winsw/releases]

I recommend that you this project the copy it on disc C:\

Check the paths on:
- C:\nginx\php\php-7.4.10\phpservice.xml
- C:\nginx\nginxservice.xml

### Install ###
In the path C:\nginx\php\php-7.4.10\ run the next command with permissions of admin

```sh
$ .\phpservice.exe install
```

In the path C:\nginx\ run the next command with permissions of admin

```sh
$ .\nginxservice.exe install
```

### Start services ###
```sh
$ net start nginx
$ net start php
```
`
### Stop services ###
```sh
$ net stop nginx
$ net stop php
```

I using MariaDB, here is the installer
- MariaDB [https://mariadb.com/downloads/]


### PHP extensions enabled: ###
- extension=pdo_mysql
- extension=fileinfo
- extension=curl
- extension=gettext
- extension=imap
- extension=gd2
- extension=mbstring
- extension=mysqli
- extension=openssl
- extension=bz2
- extension=exif


### Create a new site with your own domain ###
- Create a new block in nginx setting with your new settings, you have to access to C:\nginx\conf\sites and create another file with the your domain name. For example, 
```sh
 
server {
	listen       80;
    server_name  luisavila.app;

    access_log  logs/luisavila.access.log;

	location / {
		root   html/luisavila.app;
		index  index.html index.htm index.php;
	}
		
	location ~ \.php$ {
		root           html/luisavila.app;
		fastcgi_pass   127.0.0.1:9999;
		fastcgi_index  index.php;
		fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
		include        fastcgi_params;
	}
}

```

- Create the new domain on hosts file in the path C:\Windows\System32\drivers\etc
 ```sh
127.0.0.1      luisavila.app 
 
```

- Ready to working 


### Create SSL Certificate ###
```sh
$ openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout /C:/nginx/ssl/localhost.key -out /C:/nginx/ssl/localhost.crt
```
- Remember use git to this step and response to the questions of the shell

