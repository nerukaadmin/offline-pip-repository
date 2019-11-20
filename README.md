# offline-pip-repository for pip and pip3 .
Create offline pip repository  using Apache server in Ubuntu/Linux .

## Getting Started
Use ubuntu or linux machine to config apache server
For Ubntu Please refr below link
https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-18-04-quickstart
Follow the steps in above link to setup apache server.

For Centos Please refer below link
https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-centos-7

Follow the steps  in above link to setup apache server.

### Dependancies.



```
pip3 or pip must be installed 
install pip2pi
using pip or pip3
using pip install pip2pi for pip3 use pip3 install pip2pi

```

### Setup Apache for pip/pip3 repo.

Create folder in /var/www/html/xxxx use what ever file name you wanted for xxxx.

    mkdir -p /var/www/html/xxxx
    chmod 777 -R /var/www/html/xxxx

### Download pip packages to use offline pacakges and making index.
```
Downolod your pip/pip3 pacakges to /var/www/html/xxxx.
use below command.
pip dwonload -d /var/www/html/xxxx/ package name
for pip3
pip3 dwonload -d /var/www/html/xxxx/ package name
```
After downolading packages create index for above foledr use following command.
```
use below command.
```
    dir2pi /var/www/html/xxxx/

```
After this new foledr will create inside /var/www/html/xxxx/ as simple it will contain index.html for packages that we downloaded
If it is done your offline pip/pip3 repo is ready to use.
For cheking purpose  go to you browser and goto : your_ip/xxxx/simple
It will display all the packages we download as list.
```

### Configure Client machines for offline pip repository.


```
Log to client machine as root.
Create dir in .pip in root directory and apply permision.
Inside .pip create pip.conf and append config settings to it.
```

    cd /
    mkdir -p .pip
    chmod 777 -R .pip
    vi /.pip/pip.conf
    [global]
    index = http://xxx.xxx.xxx.xxx/packages/simple #your appache server ip
    index-url = http://xxx.xxx.xxx.xxx/packages/simple #your appache server ip
    trusted-host = xxx.xxx.xxx.xxx #your appache server ip
```
save above config and your client is now ready to use
//**NOTE** After above config you will unable to download onlin pip packages pip install always redirect to your offlinerepo //
Finally use pip install package name which adde inside offline repo it will be insatll as usually.

```





## Author

* **Neruka Lakshitha**  - [nerukaadmin](https://github.com/nerukaadmin) 

