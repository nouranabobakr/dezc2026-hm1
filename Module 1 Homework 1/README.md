# Module 1 Homework

## Steps for solving homework

### 1. Prepare .yaml file
Write the docker-compose.yaml and run 
```
docker compose up -d
```
```
services:
  db:
    container_name: postgres
    image: postgres:17-alpine
    environment:
      POSTGRES_USER: 'postgres'
      POSTGRES_PASSWORD: 'postgres'
      POSTGRES_DB: 'ny_taxi'
    ports:
      - '5433:5432'
    volumes:
      - vol-pgdata:/var/lib/postgresql/data

  pgadmin:
    container_name: pgadmin
    image: dpage/pgadmin4:latest
    environment:
      PGADMIN_DEFAULT_EMAIL: "pgadmin@pgadmin.com"
      PGADMIN_DEFAULT_PASSWORD: "pgadmin"
    ports:
      - "8080:80"
    volumes:
      - vol-pgadmin_data:/var/lib/pgadmin

volumes:
  vol-pgdata:
    name: vol-pgdata
  vol-pgadmin_data:
    name: vol-pgadmin_data
```


### 2. Create Virtual envirnoment using venv

We create a virtual envirnoment when we want to use python with diff libraries for a project
```
mkdir dez-hw1
cd dez-hw1
python -m venv venv
source venv/bin/activate
pip install pandas pyarrow sqlalchemy psycopg2-binary
```


### 3. Install Jupyter
Its better to install with pip inside virtual envirnoment then system-wide with sudo apt install jupyter

```
pip install jupyter
jupyter notebook
```


### 4. Read Data and Load into postgres
Using sqlalchemy psycopg2-binary pandas libraries


### 5. Login to pgadmin 
Go to http://localhost:8080/ and login, now we can write sql queries on our tables

Create new server     
Enter Sever Name      
Enter Host, User and Password (found in docker-compose.yaml)









