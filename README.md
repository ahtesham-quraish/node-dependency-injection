# Dependency Injection in Node with awilix

This repository contains sample code on how to do dependency injection with the [awilix](https://github.com/jeffijoe/awilix) framework.



# How to run this application

## Running the project

### Install dependencies

Make sure to install the dependencies with `npm`

```
npm install
```

### Running a local Postgres instance

Make sure that you have a local Postgres instance running and that you execute the `SQL` statement in the `migrations` directory.

After you have created the tables, make sure that you update the `config/index.js` file with your Postgres configuration (hostname, port, password, etc)

### Starting up the local server

You can then run the project by executing

```
npm run dev
```

## API

### POST /dev

Expected payload

```
{
    "email": "john@example.com",
    "firstName": "John",
    "middleNames": "Alexander Tom",
    "lastName": "Smith"
}
```

The server will return a `400` bad request error if the request body does not conform to the expected DTO (data transfer object).

This endpoint will normalize the `firstName` field by truncating the whitespace and by moving all names after the first space to the middle names field.

Please check out the `./dto` directory to learn more about the expected request body.

### GET /dev/:id

`GET /dev/:id` returns a developer associated with the specified `id`.
Response format:

```
{
    "email": "john@example.com",
    "firstName": "John",
    "middleNames": "Alexander Tom",
    "lastName": "Smith"
}
```
