
grep ^NAME /etc/*release

touch /etc/yum.repos.d/mongodb-org-5.0.repo

#Copy the following content into the above file.

[mongodb-org-5.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/amazon/2/mongodb-org/5.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-5.0.asc


sudo yum install -y mongodb-org

# Alternatively, to install  specific version of mongodb ,use below command.
sudo yum install -y mongodb-org-5.0.6 mongodb-org-database-5.0.6 mongodb-org-server-5.0.6 mongodb-org-shell-5.0.6 mongodb-org-mongos-5.0.6 mongodb-org-tools-5.0.6


# start mongodb
sudo systemctl start mongod

# To reload mongodb daemon
sudo systemctl daemon-reload

# To restart the mongodb after server reboot.
sudo systemctl daemon-reload

# To stop mongodb.
sudo systemctl stop mongod

# To restart the mongodb.
sudo systemctl restart mongod

