
Easy Guide "How to Install ABE For BGC"
============================================

1. install Req. programs
---------------------------

sudo apt-get install mysql-client mysql-server python-mysqldb python-crypto


2. Create Table & User 
------------------------

mysql -u root -p

create database abe;

CREATE USER '%USERNAME%'@'localhost' IDENTIFIED BY '%PASSWORD%';

grant all on abe.* to %USERNAME%;

quit

3. Install Scrypt Crypto Module
------------------------------------

sudo apt-get install python-all-dev

cd litecoin_scrypt

sudo python setup.py install


4. Install & Run 
------------------

sudo python setup.py install

(At First Time)
python -m Abe.abe --config abe-bgc.conf --commit-bytes 100000 --no-serve 

python -m Abe.abe --config abe-bgc.conf

5. Modify some field in abe-bgc.conf
-------------------------------------

default-loader = blkfile

dbtype MySQLdb

connect-args {"user":"%USERNAME%","db":"abe","passwd":"%PASSWORD%"}
#Change to YOUR DB ACCOUNT 

upgrade

port 12345
#Change Port

host 127.0.0.1 
#Change IP

datadir = /home/%USERNAME%/.bitgoldcoin 
#Add your Unix Account Name


6. Connect from Your Internet Browser
-----------------------------------------

http://localhost:12345


7. Enjoy Your Life!!
----------------------
