## mongoDB
One of the most popular nosql document-oriented dbs.

## Features
- uses collections, not databases
- uses documents, not tables
- dynamic: can modify the schema of any document in any document with affecting other objects inside the collection
- geospatial queries
- ACID being nosql (most are BASE: availability over consistency)

## Docker
1. Pull the image
```
sudo docker pull mongo
```
2. Run the image
```
sudo docker run --network "host" -d --name mongo -e MONGO_INITDB_ROOT_USERNAME="mongoadmin" -e MONGO_INITDB_ROOT_PASSWORD="secret" -p 27017:27017 -v "/var/lib/mongodb/data:/data/db" mongo:latest
``` 
Setting host for network parameter is needed, because mongo by default only works with 127.0.0.1. This is different from postgresql.

## Connection
Firstly, install mongo dependencies
```
sudo apt install mongodb
```
Then, use either mongo or mongosh to log in:
```
mongo(sh) --host hostname (if not runing on local) -u "mongoadmin" -p "secret" --authenticationDatabase admin
```

## hostname parameter
Please, follow same logic as per postgres configuration: https://github.com/ibasa14/postgreSQL-Tutorial