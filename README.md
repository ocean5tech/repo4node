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
  不好用就试试 sudo systemctl restart postgresql
  不好用就试试 
  sudo apt-get update
  sudo apt-get install -yqq daemonize dbus-user-session fontconfig
  sudo daemonize /usr/bin/unshare --fork --pid --mount-proc /lib/systemd/systemd --system-unit=basic.target
  exec sudo nsenter -t $(pidof systemd) -a su - $LOGNAME


ref:
https://ubuntu.com/server/docs/databases-postgresql
https://www.linuxtopic.com/2021/11/system-has-not-been-booted-with-systemd.html
https://mehmetozanguven.github.io/container/2021/12/15/running-postgresql-with-podman.html

改了下面的配置文件之后，podman search postgres才好用
$ sudo vim /etc/containers/registries.conf
unqualified-search-registries = ["registry.fedoraproject.org", "registry.access.redhat.com", "registry.centos.org", "docker.io"]


sudo apt-get -y update
sudo apt-get -y install podman

数据库
podman pull docker.io/library/postgres

 mkdir /home/wuyang/postgres_docker
 podman run -dt --name my-postgres -e POSTGRES_PASSWORD=123456 -v "/home/wuyang/postgres_docker:/var/lib/postgresql/data:Z" -p 5432:5432 postgres

podman exec -it my-postgres bash
psql -U postgres
\l

node安装
https://platformengineer.com/podman-run-node-js-express-server/
