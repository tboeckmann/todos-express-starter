# todos-express-mailchain

This app illustrates how to use [Passport](https://www.passportjs.org/) with
[Express](https://expressjs.com/) to sign users in with [Mailchain](https://mailchain.com).
Use this example as a starting point for your own web applications.

## Quick Start

To run this app, clone the repository and install dependencies:

```bash
$ git clone https://github.com/tboeckmann/todos-express-mailchain.git
$ cd todos-express-email
$ npm install
```

This app must be configured with a Mailchain Secret Recovery Phrase.

Once credentials have been obtained, create a `.env` file and add the following
environment variables:

```sh
FROM_ADDRESS=user@mailchain.com
SECRET_RECOVERY_PHRASE=__INSERT_SECRET_RECOVERY_PHRASE__
```

Start the server.

```bash
$ npm start
```

Navigate to [`http://localhost:3000`](http://localhost:3000).

## Tutorial

Follow along with the step-by-step [Mailchain Magic Link Tutorial](https://github.com/tboeckmann/www.passportjs.org/tree/mailchain-tutorial/books/tutorials/mailchain)
to learn how this app was built.

## Overview

This app illustrates how to build a todo app with sign in functionality using
Express, Passport, and the [`passport-magic-link`](https://www.passportjs.org/packages/passport-magic-link/)
strategy.

This app is a traditional web application, in which application logic and data
persistence resides on the server.  HTML pages and forms are rendered by the
server and client-side JavaScript is not utilized (or kept to a minimum).

This app is built using the Express web framework.  Data is persisted to a
[SQLite](https://www.sqlite.org/) database.  HTML pages are rendered using [EJS](https://ejs.co/)
templates, and are styled using vanilla CSS.

When a user first arrives at this app, they are prompted to sign in.  To sign
in, the user clicks a magic link that is sent to their Mailchain address via
[Mailchain](https://mailchain.com/)'s API.  Once authenticated, a login session is
established and maintained between the server and the user's browser with a
cookie.

After signing in, the user can view, create, and edit todo items.  Interaction
occurs by clicking links and submitting forms, which trigger HTTP requests.
The browser automatically includes the cookie set during login with each of
these requests.

When the server receives a request, it authenticates the cookie and restores the
login session, thus authenticating the user.  It then accesses or stores records
in the database associated with the authenticated user.

## License

[The Unlicense](https://opensource.org/licenses/unlicense)

## Credit

Created by [Jared Hanson](https://www.jaredhanson.me/)
Adapted for Mailchain by [Tim Boeckmann](https://github.com/tboeckmann/)