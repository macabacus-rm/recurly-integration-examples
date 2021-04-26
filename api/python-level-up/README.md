## API example: Python + Flask

This small application demonstrates how you might set up a web server
using Python and [Flask][flask] with RESTful routes to accept your Recurly.js
form submissions and use the tokens to create and update customer billing
information without having to handle credit card data.

This example makes use of the official Recurly [Python client library][client]
for API v3.

Note that it is not necessary to use the Flask framework. In this example it is
used to organize various API actions into distinct application routes, but one
could just as easily implement these API actions within another application
framework.

### Routes

- `POST` [/api/subscriptions/new](app.py#L29-L68)
- `POST` [/api/accounts/new](app.py#L84-L103)
- `PUT` [/api/accounts/:account_code](app.py#L106-L118)

### Use

#### Docker

1. If you haven't already, [install docker](https://www.docker.com/get-started).

2. Update the values in docker.env at the (root of the repo)[https://github.com/recurly/recurly-integration-examples/blob/main/docker.env]

3. Run `docker-compose up --build`

4. Open [http://localhost:9001](http://localhost:9001)

#### Local

1. Start the server

  ```bash
  $ pip install -r requirements.txt
  $ FLASK_APP=app.py flask run -p 9001
  ```
2. Open [http://localhost:9001/index.html](http://localhost:9001/index.html)

[flask]: http://flask.pocoo.org/
[client]: http://github.com/recurly/recurly-client-python
