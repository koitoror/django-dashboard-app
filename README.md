# django-dashboard-app

**Project**: analytics dashboard

**Description**: analytics dashboard is a Django-powered app with interactive pivot tables & charts in one centralised database.

## Getting Started

git clone the repo

### Prerequisites

A postgres/sqlite database is required for development
Install pipenv using Homebrew, Linuxbrew or pip
optionally you can use virtualenv

```shell
brew install pipenv
pip install pipenv
```

**Setting up the database with a user who has all privileges**

```sql
sudo -u postgres psql
postgres=# create database your_database;
postgres=# create user your_username with encrypted password 'your_password';
postgres=# grant all privileges on database your_database to your_username;
'a pre-populated sqlite db is provided for development'
```

### Contents of .env file

```python
DEBUG=True
SECRET_KEY='your-secret-key-here'
DATABASE_URL=psql://user:password@127.0.0.1:5432/database_name
```

## Running the app

cd into the django-dashboard-app folder

```python
cd django-dashboard-app/
```

Run the command to install all requirements from Pipfile.lock

```python
pipenv install
```

To activate the virtual environment run the command below

```python
pipenv shell
```

Make the prerequisite database migrations

```python
python manage.py migrate
```

Run the application by starting the server

```python
python manage.py runserver
```

## Running the tests

```python
cd django-dashboard-app/
python manage.py test
```

In case you do not have permission to create a database run the following command on psql

```sql
sudo -u postgres psql
ALTER ROLE your_username CREATEDB;
```

Running tests with coverage

```python
cd django-dashboard-app/
coverage run --source="." manage.py test
coverage report
```

## Built With

- [Django Rest Framework](https://www.django-rest-framework.org/) - Django

## API Endpoints Documentation

[FRONTEND & API Documentation](https://dashboard-ke.herokuapp.com/dashboard/) - DASHBOARD FRONTEND UI

## Author

- **Daniel Kamar**

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
