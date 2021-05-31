# Useful Tips

This repository is simply a place for me to store useful information.

## Ubuntu Commands and Package Commands

### Ubuntu General

- `sudo apt-get update` updates local database with package updates
- `sudo apt-get upgrade` upgrades packages to match local database
- `sudo apt-get install {{ package name }}` install a package
- `sudo apt-get autoremove` remove old unused packages
- `sudo apt remove {{ package name }}` uninstall a package
- `sudo apt list --installed` list all installed packages
- `sudo reboot` restart
- `sudo netstat -lp` check active ports
- `htop` Task manager

### Services

- `sudo service {{ service name }} {{ start/status/stop }}` stop, status or start a service
- `sudo systemctl enable {{ service name }}` enable a service
- `sudo systemctl start {{ service name }}` start a service
- `sudo systemctl status {{ service name }}` services status
- `/etc/systemd/system/` create service files here

### CERTBOT

- `certbot certificates` view cert information
- `certbot renew` renew certs

### UFW

- `sudo ufw allow {{ port }}/tcp` allow a port
- `sudo ufw deny {{ port }}/tcp` deny a port
- `sudo ufw status` port status
- `sudo ufw allow from {{ ip }} to any port {{ port }} comment 'somecomment'` allow ip to port
- `sudo ufw status numbered` list all rules with numbered index (to be used to delete)
- `sudo ufw delete {{ rule index }}` delete a firewall index

### Logs

- `sudo journalctl -fu {{ service name }} --since "2016-10-18" --until "2016-10-18 04:00` View log for a service. Since and until optional. Can aluse use --since today and --until 1 hour ago
- `journalctl --disk-usage` find out how much disk space logs are using
- `sudo journalctl --vacuum-size=1K`
- `sudo journalctl --vacuum-files=0`

### NGINX

- `sudo nginx -s reload` restart the server. Usefull after config change
- `sudo nginx -t` check config syntax

### Node PM2

NPM package used to manage node processes and create systemctl services https://www.npmjs.com/package/pm2

- `pm2 start {{ app.js }}` start any application (Node.js, Python, Ruby, binaries in $PATH...)
- `pm2 list` list all running applications
- `pm2 info {{ appname }}`
- `pm2 monit` monitor logs, custom metrics, application information
- `pm2 stop {{ appname/id }}`
- `pm2 restart {{ appname/id }}`
- `pm2 delete {{ appname/id }}`
- `pm2 logs {{ appname }}`
- `pm2 flush` flush logs
- `pm2 show {{ appname/id }}`
