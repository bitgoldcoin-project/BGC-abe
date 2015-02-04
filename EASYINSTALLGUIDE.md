
Easy Guide "How to Install ABE For BGC"
============================================

1. install Req. programs
---------------------------

1) MysqlDB
sudo apt-get install mysql-client mysql-server python-mysqldb python-crypto

2) PostgreSQLDB
sudo apt-get install python2.7 python-crypto postgresql-8.4 python-psycopg2


2. Create Database 
------------------

1) Mysql

mysql -u root -p

create database abe;

CREATE USER '%USERNAME%'@'localhost' IDENTIFIED BY '%PASSWORD%';

grant all on abe.* to %USERNAME%;

quit

2) PostgreSQL

sudo -u postgres createdb abe
sudo -u postgres createuser %USERNAME%

Add the following line to /etc/postgresql/*/main/pg_hba.conf:

    local abe %USERNAME% ident

Issue:

    sudo service postgresql reload


3. Install Scrypt Crypto Module
------------------------------------

sudo apt-get install python-all-dev

cd litecoin_scrypt

sudo python setup.py install

4. Modify some field in abe-bgc.conf
-------------------------------------

default-loader = blkfile

1) MYSQL DB
dbtype MySQLdb 
connect-args {"user":"%USERNAME%","db":"abe","passwd":"%PASSWORD%"}
(Change to YOUR DB ACCOUNT)

2) PostgreSQL DB
dbtype psycopg2
connect-args {"database":"abe"}

upgrade

port 12345
(Change Port)

host 127.0.0.1 
(Change IP)

datadir = /home/%USERNAME%/.bitgoldcoin 
(Add your Unix Account Name)

5. Install & Run 
------------------

sudo python setup.py install

(At First Time)
python -m Abe.abe --config abe-bgc.conf --commit-bytes 100000 --no-serve 

python -m Abe.abe --config abe-bgc.conf


6. Connect from Your Internet Browser
-----------------------------------------

http://localhost:12345


7. Enjoy Your Life!!
----------------------
