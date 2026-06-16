

DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASS=posts_pass_123
DB_NAME=blog_db
JWT_SECRET=supersecret
JWT_EXPIRES_IN=3600s

MONGO_URI=mongodb://localhost:27017/integrador


CREATE DATABASE blog_db;
ALTER ROLE postgres SET client_encoding TO 'utf8';
ALTER ROLE postgres SET default_transaction_isolation TO 'read committed';
ALTER ROLE postgres SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE blog_db TO postgres;
GRANT ALL ON SCHEMA public TO postgres;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON TABLES TO postgres;
ALTER DATABASE blog_db OWNER TO postgres;
ALTER SCHEMA public OWNER TO postgres;
GRANT CREATE ON SCHEMA public TO postgres;


sudo systemctl restart mongod
mongosh
use admin
db.createUser({
    user: "user_consultorio_mongo",
    pwd: "user_consultorio_mongo_123",
    roles: [{ role: "root", db: "admin" }]
})
use posts_db_mongo

ssh-keygen -t ed25519 -C "varas_consultorio-deploy" -f ~/.ssh/github_deploy_varas


postgres=# CREATE DATABASE consultorio_odontologico_db_pg;
\c consultorio_odontologico_db_pg
CREATE USER consultorio_odontologico_user_pg WITH PASSWORD 'consultorio_odontologico_pass_123';
ALTER ROLE consultorio_odontologico_user_pg SET client_encoding TO 'utf8';
ALTER ROLE consultorio_odontologico_user_pg SET default_transaction_isolation TO 'read committed';
ALTER ROLE consultorio_odontologico_user_pg SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE consultorio_odontologico_db_pg TO consultorio_odontologico_user_pg;
GRANT ALL ON SCHEMA public TO consultorio_odontologico_user_pg;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON TABLES TO consultorio_odontologico_user_pg;
ALTER DATABASE consultorio_odontologico_db_pg OWNER TO consultorio_odontologico_user_pg;
ALTER SCHEMA public OWNER TO consultorio_odontologico_user_pg;
GRANT CREATE ON SCHEMA public TO consultorio_odontologico_user_pg;
CREATE DATABASE
invalid integer value "consultorio_odontologico_user_pg" for connection option "port"
Previous connection kept
postgres=# CREATE DATABASE blog_db;
\c blog_db
CREATE USER postgres WITH PASSWORD 'posts_pass_123';
ALTER ROLE postgres SET client_encoding TO 'utf8';
ALTER ROLE postgres SET default_transaction_isolation TO 'read committed';
ALTER ROLE postgres SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE blog_db TO postgres;
GRANT ALL ON SCHEMA public TO postgres;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON TABLES TO postgres;
ALTER DATABASE blog_db OWNER TO postgres;
ALTER SCHEMA public OWNER TO postgres;
GRANT CREATE ON SCHEMA public TO postgres;
CREATE DATABASE
invalid integer value "postgres" for connection option "port"
Previous connection kept
postgres=# CREATE DATABASE blog_db;
ERROR:  database "blog_db" already exists
postgres=# \c blog_db postgres
You are now connected to database "blog_db" as user "postgres".
blog_db=# ALTER ROLE postgres SET client_encoding TO 'utf8';
ALTER ROLE postgres SET default_transaction_isolation TO 'read committed';
ALTER ROLE postgres SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE blog_db TO postgres;
GRANT ALL ON SCHEMA public TO postgres;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON TABLES TO postgres;
ALTER DATABASE blog_db OWNER TO postgres;
ALTER SCHEMA public OWNER TO postgres;
GRANT CREATE ON SCHEMA public TO postgres;
ALTER ROLE
ALTER ROLE
ALTER ROLE
GRANT
GRANT
ALTER DEFAULT PRIVILEGES
ALTER DATABASE
ALTER SCHEMA
GRANT
blog_db=# exit


GIT_SSH_COMMAND='ssh -i ~/.ssh/github_deploy' git clone git@github.com:usuario/repositorio.git /root/nestjs-blog-backend
cd /root/nestjs-blog-backend