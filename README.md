<img alt="Turso Logo" src="https://github.com/tursodatabase/.github/raw/main/profile/turso-banner.png" width="1000">

# Epic Stack with Turso


This is an example of how to integrate [Turso](https://turso.tech/) database with the Epic Stack.

## Create a Turso Database

Create a database called `epic-stack-example`:

```
turso db create epic-stack-example
```

## Set Environment Variables
You need to add the database url and access token as environment variables:

```
TURSO_DATABASE_URL=
TURSO_AUTH_TOKEN=
```

You can get both on the [web app](https://turso.tech/app/databases) or using the [Turso CLI](https://docs.turso.tech/cli/introduction).

To get the URL of your database using the CLI, run the command below and set the result to `TURSO_DATABASE_URL`:

```
turso db show epic-stack-example --url
```

In the same way, get a database token and set its value to `TURSO_AUTH_TOKEN` by running the command below:

```
turso db tokens create epic-stack-example
```

## Seed Your Database

Seed your database with this command:

```
turso db shell epic-stack-example < prisma/migrations/20230914194400_init/migration.sql
```

## Migrations

To apply migrations to your database, run the `migrate` command:

```
npx prisma migrate dev --name add_subtitle_to_notes
```

Then, copy the migration file path from the new migration folder and run `turso db shell`:

```
turso db shell epic-stack-example < prisma/migrations/20240402084116_add_subtitle_to_notes/migration.sql
```
