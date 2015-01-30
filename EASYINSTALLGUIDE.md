
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

apt-get install python-all-dev

cd litecoin_scrypt

python setup.py install


4. Install & Run 
------------------

sudo python setup.py install

(At First Time)
python -m Abe.abe --config abe-bgc.conf --commit-bytes 100000 --no-serve 

python -m Abe.abe --config abe-bgc.conf


5. Connect from Your Internet Browser
-----------------------------------------

http://localhost:12345


6. Enjoy Your Life!!
----------------------
