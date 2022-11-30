# Designing and Operating a Singe Service with Docker

This section is 3 chapters for creating a single microservice.

- first they create the REST service implemented in python
- then performs the steps to create a docker container
- then creates a pipeline to ensure the service always complies with high quality standards

## Creating a REST service with Python

for any externally available backend resources, you need to identify what security is needed. In the book this is performed by Java Web Tokens.

**NOTE**: when designing your REST service, be sure to anticipate which endpoints can be external and accessed without logging in, like the search function for this blog site. You don't need to be logged in to use the search bar on most web sites.

A restful service means that the universal resource identifiers represent resources and the HTTP methods are used to perform actions on those resources. Requests need to be stateless, that is, independent of any other request made to the service.

Use the [12-factor principles](https://12factor.net/)to improve your database / data model design when converting to a microservice architecture.

IN planning the API, you should outline the resources, URI paths, and HTTP methods applicable to each resource in the data model. Public API access should have the prefix `api/` to the URI path. Admin should have `admin/`.

## Database Requests

There are several packages in python that provide object relational mappers to database functionality:

- PonyORM
- the python API database specification (PEP 249)
- Django's ORM
- SQLalchemy not as easy as django, but allows you to map an ORM to an existing database.
  - the example in the book will be trivial, but this is incredibly useful when doing legacy migrations.
  - Easier to learn from the flask-sqlalchemy library instead of directly from the main sqlalchemy library at first.

Also, Flask-RESTPlus is an extension to flask that allows for implementing REST services, and is small, easy to use, and compatible with the usual tech stack of web applications, since it uses the web server gateway interface protocol (wsgi).

Flask can do restful services, but Flask-RESTPlus adds some very useful capabilities that allow for good developing practices and speed of development.

FLask-RESTPlus has the following features:

- defines namespaces which are ways of creating prefixes and structuring the code. Assists with long term maintenance and helps with the design when creating a new endpoint.
- has a full solution for parsing input parameters.
- In the same way, it has a serialization framework. The serialization also defines objects that can be reused, and can mask certain fields in returning data, to allow for sending partial objects.
- It has full swagger documentation support.
- There's a pytest-flask module to create tests and add some fixtures ready to work iwth a flask application.
