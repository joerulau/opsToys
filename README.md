# opsToys

Fork of OneinStack, but is a custom image source.

## Installation

Install the dependencies for your distro, download the source and run the installation script.

#### CentOS/Redhat

```bash
yum -y install wget screen
```

#### Debian/Ubuntu

```bash
apt-get -y install wget screen
```

#### Download Source and Install

Modify [mirror_link](https://github.com/qiaoro/opsToys/blob/main/options.conf), replace it with a source trust

```bash
mkdir opsToys
cd opsToys
git clone -b main https://github.com/qiaoro/opsToys.git
./install.sh
```

If you disconnect during installation, you can execute the command `screen -r opsToys` to reconnect to the install window
```bash
screen -S opsToys
```

If you need to modify the directory (installation, data storage, Nginx logs), modify `options.conf` file before running install.sh
```bash
./install.sh
```

## How to install another PHP version

```bash
~/opsToys/install.sh --mphp_ver 54

```

## How to add Extensions

```bash
~/opsToys/addons.sh

```

## How to add a virtual host

```bash
~/opsToys/vhost.sh
```

## How to delete a virtual host

```bash
~/opsToys/vhost.sh --del
```

## How to add FTP virtual user

```bash
~/opsToys/pureftpd_vhost.sh
```

## How to backup

```bash
~/opsToys/backup_setup.sh    // Backup parameters
~/opsToys/backup.sh    // Perform the backup immediately
crontab -l    // Can be added to scheduled tasks, such as automatic backups every day 1:00
  0 1 * * * cd ~/opsToys/backup.sh  > /dev/null 2>&1 &
```

## How to manage service

Nginx/Tengine/OpenResty:
```bash
systemctl {start|stop|status|restart|reload} nginx
```
MySQL/MariaDB/Percona:
```bash
systemctl {start|stop|restart|reload|status} mysqld
```
PostgreSQL:
```bash
systemctl {start|stop|restart|status} postgresql
```
MongoDB:
```bash
systemctl {start|stop|status|restart|reload} mongod
```
PHP:
```bash
systemctl {start|stop|restart|reload|status} php-fpm
```
Apache:
```bash
systemctl {start|restart|stop} httpd
```
Tomcat:
```bash
systemctl {start|stop|status|restart} tomcat
```
Pure-FTPd:
```bash
systemctl {start|stop|restart|status} pureftpd
```
Redis:
```bash
systemctl {start|stop|status|restart|reload} redis-server
```
Memcached:
```bash
systemctl {start|stop|status|restart|reload} memcached
```

## How to upgrade

```bash
~/opsToys/upgrade.sh
```

## How to uninstall

```bash
~/opsToys/uninstall.sh
```

## Installation