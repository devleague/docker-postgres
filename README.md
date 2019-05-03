### Start the database

**Ensure that your .env is setup correct**

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
