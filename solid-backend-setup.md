### How to setup a s.o.l.i.d. Backend

1. Install `docker-compose` via the appropriate methode for your OS. See [here](https://docs.docker.com/compose/install/).
2. Clone the repository you wish to build from our Github organization [here](https://github.com/zentrumnawi) and make sure to checkout the correct branch.
3. If you develop on Windows, be aware of line endings. The following steps might fail if some of the files are saved with CLRF endings.
4. Now build all containers by excuting `docker-compose build`.
5. Migrate the database with `docker-compose run --rm web python manage.py migrate`
6. Create a superuser aka admin account: `docker-compose run --rm web python manage.py createsuperuser`. You will be prompted to provide a username and password (rest ist not mandatory).
7. Start the containers with `docker-compose up` (`-d` flag for detached mode).
8. The Api is now available under `localhost:8000`.
9. The admin interface can now be accessed via `localhost:8000/admin`with the prior created admin account.
