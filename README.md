# Persondemo-Spring-App
Springboot + Postgresql + Docker Demo App

## Folder Structure
### `src`:
- `main`
- `test` (empty currently)

### `src/main/resources`: 
- `db.migration`
    - SQL code to create table
- `application.yml`
    - Configure the postgresql database

### `src/main/java/com.example.demo`
- `DemoApplication` 
    - Main function
- `datasource` 
    - Bean to connect db with Docker and yml file.
- `model` 
    - Domain `Person` object that represent the data 
    being stored and retrieved by the application.
   
- `dao`
    - Contains data access objects that perform 
    db operations and interact with the database
    - `PersonDao`
        - Interface 
    - `FakePersonDataAccessService`
        - "fakeDao", a mock database DAO that 
        implements `PersonDao`
    - `PersonDataAccessService`
        - "postgres", a Postgresql DAO that 
        implements `PersonDao`
- `service`
    - Contains service class that performs business logic and interact
    with DAOs to perform database operations.
    - Currently connected to "postgres", `PersonDataAccessService`.
- `api`
    - Contains controllers that handle incoming HTTP req and 
    delegate to the corresponding `dao`(postgres).
### `pom.xml` 
- Building Maven-base java project and managing its
    dependencies.
