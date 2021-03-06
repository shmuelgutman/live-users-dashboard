# Live-users-dashbaord

A demo project that illustrates a full-stack nodejs and react application.

The backend and frontend are completely separated and should be run in different processes.

### First run the backend:
`cd backend && npm i && npm start`  
### Environment variables:  

* EXPRESS_PORT - default to 8080
* SQLITE_FILE - path to file location or `:memory:`. default to `./db/live-users.db`
* JWT_EXPIRES_IN - default to 1 hour.
* JWT_SECRET
* PASSWORD_HASH_KEY

### Backend endpoints:

* `POST /register` - register a new user.  
body: `{"username": "user1", "password": "1234"}`  
response: `{"jwt": "<token>"}` - jwt token to authenticate requests using `Authorization` header `Bearer <token>`

* `POST /login` - login a registered user.  
body: `{"username": "user1", "password": "1234"}`  
response: `{"jwt": "<token>"}` - jwt token to authenticate requests using `Authorization` header `Bearer <token>`

* `POST /logout` - log the user out.  
Since the jwt is maintained only client side, there is no real reason the add this endpoint. The client-side should just delete the jwt from the local-storage. 

* `GET /api/me` - get the current authenticated user.

* `GET /api/users` - get online users.

### Tests:  
`cd backend && npm run test`


## Frontend

Then run the frontend in a different terminal window:

`cd frontend && yarn && yarn start`

Run Test:
  
`yarn test`

The frontend simply have 3 views: login, register and dashboard.  
Go to the register view and sign-up with some username and password.  
View the user in the dashboard.  
Open the app in a different tab and register with another user.  
See the online users table live-updated in first tab.  
