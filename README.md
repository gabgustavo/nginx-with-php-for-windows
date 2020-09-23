<p align="center">
<img src="https://i.ytimg.com/vi/uuutAIRFSec/maxresdefault.jpg" width="400">
</p>

# This project contains Nginx with PHP and WinSW.NET2#
- Nginx 1.18.0 Stable version - [https://nginx.org/en/download.html][PlGa]
- Php7.4.10 - [https://windows.php.net/download/][PlGa]
- WinSW v2.10.2 - [https://github.com/winsw/winsw/releases][PlGa]

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


