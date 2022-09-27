# install-postgress-sql-and-remote-connection

1,sudo apt update

2,sudo apt install postgresql postgresql-contrib

3,sudo systemctl start postgresql.service

4,sudo -i -u postgres

#How to create a user with PSQL

1,sudo -u postgres createuser <name> --pwprompt

2,sudo -u postgres createuser <name> -P

#Give all permissions to a user on a PostgreSQL database

1,GRANT CONNECT ON DATABASE my_db TO my_user;

#Configure PostgreSQL to allow remote connection

1,find / -name "postgresql.conf"

2,/var/lib/pgsql/9.4/data/postgresql.conf

3,Open postgresql.conf file and replace line listen_addresses = 'localhost'  with   listen_addresses = '*'

4,Now restart postgresql server.

5, netstat -nlt

6,In order to fix it, open pg_hba.conf and add following entry at the very end.


host    all             all              0.0.0.0/0                       md5
host    all             all              ::/0                            md5


7,Restart postgresql server.

