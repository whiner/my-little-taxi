# my-little-taxi
Small twisted web server

apt-get install mysql-service python-mysqldb
pip install -r requirements.txt

# start database
sudo mysqld --init-file init_db.sql

python server.py

# set car location
curl --request POST 'http://localhost:8090/car?id=42&ll=37.412021,11.896277'
# get car location (todo: subscribe)
curl --request GET  'http://localhost:8090/car?id=42'
# get nearest cars
curl --request GET 'http://localhost:8090/nearest_cars?ll=37.412021,11.896277&count=11'