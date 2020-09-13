# Overview

Master repo for the WFO scheduler application.

The frontend and the backend are included as git submodules. You can find the standalone frontend repo [here](https://github.com/DDavidkov/wfo-scheduler-frontend) and the backend repo [here](https://github.com/DDavidkov/wfo-scheduler-backend).

# Prerequisites

- [NodeJS](https://nodejs.org/en/) - Latest stable (LTS) should be good enough
- [PostgreSQL](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads) - Download and install 11.9
- [PgAdmin](https://www.pgadmin.org/download/pgadmin-4-windows/) - I am using v4.23, but latest should be fine as well. Note: you don't need this step if you have installed it as part of the PostgreSQL installation.
- [VSCode](https://code.visualstudio.com/) - Latest stable

# How to run

1. Run _git submodule init_ and _git submodule update_ from a command prompt

2. Install the dependencies by running _npm install_ from this folder and the wfo-scheduler-backend and wfo-scheduler-frontend folders

3. Create a .env file in the backend and copy the contents of the .env.example file from the same folder. You may need to change some of the stuff there like the DB_PASS field in order to match you PostgreSql password. Additionally you can generate a safer JWT_SECRET from [this](https://www.grc.com/passwords.htm) site (use the value generated in the 63 chars alpha numeric field).

4. Create a .env.local file in the frontend, by copying the contents of the .env.example file from the same folder.

5. Open PgAdmin and create a new database with the same name as the DB_NAME field from your .env file in the backend (by default it should be wfo). Right click the newly created db and select the "Restore" option. Use the backup file in the backend data folder for the restore. You can now browse the available employees in the db.

6. Run _npm start_ command from this folder and the application should start in your browser. You can log with the email of the employees in the db and "test" for password (this is the password for all employees).
