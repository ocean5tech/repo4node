# repo4node

# Ubuntu配置


sudo apt-get update
sudo apt-get upgrade
sudo apt install postgresql
cd /etc/postgresql/14/main
sudo vi postgresql.conf
edit -> listen_addresses = '*'


cd /etc/postgresql/14/main
sudo -u postgres psql template1

sudo systemctl restart postgresql


ref:
https://ubuntu.com/server/docs/databases-postgresql
https://www.linuxtopic.com/2021/11/system-has-not-been-booted-with-systemd.html
