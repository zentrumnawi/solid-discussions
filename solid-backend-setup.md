### How to setup a s.o.l.i.d. Backend

1. Install `docker-compose` via the appropriate methode for your OS. See [here](https://docs.docker.com/compose/install/).
2. Clone the repository you wish to build from our Github organization [here](https://github.com/zentrumnawi) and make sure to checkout the correct branch.
_Hint: If you develop on Windows, be aware of line endings. The following steps might fail if some of the files are saved with CLRF endings._
3. Now build all containers by excuting `docker-compose build`.
4. Migrate the database with `docker-compose run --rm web python manage.py migrate`
5. Create a superuser aka admin account: `docker-compose run --rm web python manage.py createsuperuser`. You will be prompted to provide a username and password (rest ist not mandatory).
6. Start the containers with `docker-compose up` (`-d` flag for detached mode).
7. The Api is now available under `localhost:8000`.
8. The admin interface can now be accessed via `localhost:8000/admin`with the prior created admin account.
