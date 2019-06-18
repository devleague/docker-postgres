### Create a .env File

Create a .env file by copying the contents of the .env.example file into the .env file.

This file should contain the following:

```
DOCKERHUB_NAME=username
IMAGE_NAME=docker-postgres
IMAGE_VERSION=0.0.1

POSTGRES_HOST_PORT=5432
POSTGRES_CONTAINER_PORT=5432
POSTGRES_USER=username
POSTGRES_PASSWORD=password
POSTGRES_DB=database_name
```

DOCKERHUB_NAME is the username used when creating a dockerhub account.  
IMAGE_NAME is the name of the docker image we will be creating.  
IMAGE_VERSION is the version of docker image we will be creating.  

POSTGRES_HOST_PORT is the port where this container will attach to on your laptop.  
POSTGRES_CONTAINER_PORT is the port that the container will leave open outside of the container.  
POSTGRES_USER is the username of the postgres user this docker image will create during initial startup.  
POSTGRES_PASSWORD is the password for the postgres user that will be created during initial startup.  
POSTGRES_DB is the name of the database that will be created on initial startup of the container.  

Please update all key/value pair with your own relevant information except:
 - IMAGE_VERSION
 - POSTGRES_HOST_PORT
 - POSTGRES_CONTAINER_PORT


### Start the database

Then run the following command in the same folder as the docker-compose file:  
`docker-compose up`


### Connect to your database

**PSQL**  
Install a psql client using this webpage: https://www.compose.com/articles/postgresql-tips-installing-the-postgresql-client/

Run this command in your project's root directory:  
`psql -h localhost -U ${username} -d ${database_name}`  

Where username should match the POSTGRES_USER in your .env file and database_name should match POSTGRES_DB. The password that it will prompt you for should be POSTGRES_PASSWORD from your .env file as well.

**GUI**   
You can alternatively use DBeaver to connect to your PostGRES server and send queries from there but your milage may vary.

[DBeaver](https://dbeaver.io/download/)


### Run SQL file

**PSQL**  
`\i path/to/file/filename.sql`  
The path to the file that you want to execute should be written as if you're starting from the project root. 
