# database_servers_local
![build status](https://github.com/praisetompane/database_servers_local/actions/workflows/database_servers_local.yaml/badge.svg) <br>

## Objectives
- Implement docker-compose setups for common database servers to use for local development. <br>

## Project Structure

## Dependencies
- [Docker](https://docs.docker.com/get-started/)

## Usage
You can copy them into the project to share the `.env` file between your application and the database or run them from here and copy only the database credentials to your project's `.env` file.

## Run Program
- Navigate to the server you want
    ```shell
    # example if you want postgres
    cd ./mysql
    ```
- To start the system run
    ```shell
        # this might take a while on the first run, please be patient.
        # it is because it downloading the images from Docker Hub if they are not on the machine.
    ./start_system.sh
    ```

- To stop the system run
    ```shell
    ./stop_system.sh
    ```

## Database State Management

- The database state (i.e. tables, stored procedures, indexes, etc) are managed using Flyway.
    - Flyway docs:  https://documentation.red-gate.com/fd/flyway-documentation-138346877.html
    - Technical details for flyway configuration are in the docker-compose file, under `app_etl_db_flyway_migrations` service.
    - Migrations location in repo: app_etl/migrations
    - Migrations naming scheme: VYYYYMMDDHHSS
        - example: `V202310111851.sql`
    - Current database state can be queried with `select * from flyway.flyway_schema_history`

## Git Conventions
- **NB:** the master is locked and all changes must come through a Pull Request.
- commit messages:
    - provide concise commit messages that describe what you have done.
        ```shell
        # example:
        git commit -m "feat(core): algorithm" -m"implement my new shiny faster algorithm"
        ```
    - screen shot of Githb view
    - references: 
        - https://www.conventionalcommits.org/en/v1.0.0/
        - https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/
