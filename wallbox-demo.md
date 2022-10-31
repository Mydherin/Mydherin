# Wallbox demo

## Considerations

The `API URL` is `https://demo.svalvar.com`.
The `DB URL` is `https://demo-db.svalvar.com`.
The app repository is `http://github.com/Mydherin/ts-backend-ddd-skeleton`
The requests of this demo have been done using `Postman` and the `request data` have been sent in the `body` using `x-www-form-urlencoded` format.

## Demo path

Make a `GET` request to `/noresource`, you should receive a 404 status code and reponse message will be `Not found error`.

Make a `GET` request to `/status`, you should receive a 200 status code and empty response.

Make a `PUT` request to `/users` with the following fields:
  name: Wallbox
  password: P@ssw0rd
  email: email@email.com
You should receive a 200 status code and empty response.

Make the exactly the previous request again, you should receive a 400 status code and response message will be `duplicated user error`.

Make a `PUT` request to `/users` with the following fields:
  name: @Wallbox
  password: P@ssw0rd
  email: email@email.com
You should receive a 422 status code and reponse message will be `name: invalid value`.

Make a `PUT` request to `/users` with the following fields:
  name: Wallbox_Two
  password: 1234
  email: email@email.com
You should receive a 422 status code and reponse message will be `password: invalid value`.

Make a `PUT` request to `/users` with the following fields:
  name: Wallbox_Two
  password: P@ssw0rd
  email: email
You should receive a 422 status code and reponse message will be `email: invalid value`.

To check the previous user was created correctly, you can access to the db (mongo) using this link `https://demo-db.svalvar.com`. To see the users,
click on `app database` and `users` collection. Here you can checked the users that you have created. Feel free to create as many users as you want.

Thanks!
