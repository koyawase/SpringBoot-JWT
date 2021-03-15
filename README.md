# SpringBoot-JWT

Simple project to test how JWT works in Spring Boot

## How to use it

`GET` request on `localhost:8080/hello` endpoint is blocked by authentication requiring JWT token to access it.

to get the token: on Postman, send a `POST` request to `localhost:8080/authenticate` with the username and password in the body:
`{ "username": "foo", "password": "foo" }`. The username and password are currently hardcoded in `/services/MyUserDetailsService`. Ideally this will be coming from a DB, but for testing cases, this is hard coded.

After getting JWT from the post request, send `GET` request to `localhost:8080/hello` with Header: `Authorization: Bearer {jwt-token}`

This will authenticate to `/hello` endpoint.


NOTE: It does not authenticate through the browser - aka the JWT does not get stored in the browser to then authenticate `/hello` endpoint. This only works in a test environment such as Postman. Making it work in the browser could be an enhancement for the future.
