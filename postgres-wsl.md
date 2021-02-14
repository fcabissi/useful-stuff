_Instructions WIP as of 2021-02-14_

Requirements:
- WSL 2
- Ubuntu 20.04

1. Run `sudo apt update && sudo apt upgrade` to make sure everything is up to date.
2. Run `sudo apt install postgresql postgresql-contrib` to install postgres.
3. Start the postgres service with `sudo service postgresql start`
4. Log in as the "postgres" user with `sudo -i -u postgres`.
5. Create a new user with `createuser --interactive` and follow the prompts.
6. Create a new database with `createdb <database name>`.

Create/change password:

1. Log in with the "postgres" user.
2. Open psql by running `psql`.
3. To change a user (for example, the user named "carl") run `\password carl`
4. Enter the password twice.
