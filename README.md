# Django web server

## Basics

A single site is built of multiple apps.

Each app has a model is defined in models.py Python file. It is expressed as a set of Python classes extending a Model class that capture fields and keys of the data model.

This model is used to build a database schema (E.g. SQLite or PostgreSQL). Each Python class becomes a table. This is done by running "python3 manage.py sqlmigrate modelName".

Admin view for data manipulation is generated automatically based on the data model.

Django is using a simple django web server for development and testing.
For production it can use Apache.

## URL handling

Django uses URL matchers expressed as urls.py files located in the project root and in each application.
Each file defines a set of URL patterns that are matched one after another before the first match. Then Django strips the matched string and passed the rest of the URL further to the child URL matcher (E.g. to the individual app level).

## View

Each URL is eventually associated with a view.

URL patterns extract variables from URLs (for POST requests) and pass them to views as parameters.

Views are represented as Python functions that take a HttpRequest and return an HttpResponse or throw an Http404 exception.

## Templates

Templates are html fiels with a special syntax for accessing Django variables ({% instructions %}).

Views are passing dictionaries of variable names and values to templates for rendering.
