# Kittygram

### A simple app to share your cat with the world.

## Used technologies:
#### Django
#### Django REST
#### React

## Start the project:

### Clone the repository
```bash
git clone git@github.com:lopentusska/kittygram.git
```

### Create .env file with the following script
```bash
cd kittygram/
echo '''DB_NAME=kittygram_db
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_HOST=localhost
DB_PORT=5432
DJANGO_SECRET_KEY=your_secret_key
DJANGO_DEBUG=True
DJANGO_ALLOWED_HOSTS=127.0.0.1 localhost''' > .env
```

# Run project in docker:

```bash
docker compose up -d
```
#### wait some time to let docker build containers

#### logs:
```bash
docker logs <container_name> -f
```

#### stop containers:
```bash
docker compose down
```

# Run locally:

## Start backend

### postgresql
```bash
sudo su postgres
psql
CREATE DATABASE kittygram_db;
CREATE USER kittygram_user WITH PASSWORD 'kittygram_password';
GRANT ALL PRIVILEGES ON DATABASE kittygram_db TO kittygram_user;
ALTER USER kittygram_user CREATEDB;
```

### Create venv and install requirements.txt
```bash
cd backend/
python -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

### Run migrations and start server
```bash
python manage.py migrate
python manage.py runserver
```

### Optionally create superuser
```bash
python manage.py createsuperuser
```

## Start frontend
```bash
cd frontend/
npm install
npm start
```
