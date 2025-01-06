## Setup

**Note:** For this exercise, we have provided an `.env` file with the database connection string. Normally, you would not commit this file to version control. We are doing it here for simplicity and given that we are using a local SQLite database.

## Migrations

Before running the migrations, we need to create a database. We can do this by running the following command:

```bash
npm run migrate:latest
```

## Running the server

In development mode:

```bash
npm run dev
```

In production mode:

```bash
npm run start
```

## Updating types

If you make changes to the database schema, you will need to update the types. You can do this by running the following command:

```bash
npm run generate-types
```

## App Requirements

### Administrators should be able to:

For creating new screening:

1. Date must be in the future
2. movie id is required
3. timestamp of creation is required
4. no of tickets is required. 1 to 200

### Users should be able to:

1. Request a list of movies based on provided movie(s) id (e.g., /movies?id=1,2,3).
2. Request a list of screenings available with information: (timestamp, number of tickets, number of tickets left) and movie: (title and year).
3. Requost a list of booked tickets. Should return ticket Id, movie title, and sceening date.
4. Create new ticket for a screening of a movie if there are remaining spots.

### TODO

1. create table in the database for screenings(id, created_at timestamp, movie_id references movies.id, tickets_total int, tickets_taken int). Migrate. Add Types.
2. create table in the database for tickets(id, screening_id, created_at timestamp). Migrate. Add Types
3. in modules fodler make new directory for screenings and movies. Make test folders inside each module.
4. inside modules/screenings/tests make new files screenings.sepcs.ts and repository.specs.ts.
5. screenings.sepcs.ts make new tests block for screening controller requests.
6. repository.specs.ts make new tests blcok for repository request for screening list.
7. make repository.ts and controller.ts files and create basic implementation for tests to run. Make sure tests fail.
8. Write required code for screening module to pass tests.
9. Refactor if there is still time remaining.
