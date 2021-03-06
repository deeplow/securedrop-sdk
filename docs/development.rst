Development
============

We are using `pipenv <https://docs.pipenv.org>`_ to manage the dependencies of
the project.

Git clone the project repo, and use the following command to create a new dev
environment. The second command is to enable the virtual environment.

::

    pipenv install
    pipenv shell



Testing
========

The `tests` directory contains the test cases for API. We are using `vcrpy
<http://vcrpy.readthedocs.io/en/latest/>`_ to mock out the test calls.

If you want to run the tests against an actual SecureDrop environment, please
comment out the `@vcr` decorator of the `setUp` method in the test. This will
allow to have real token from the server.

To run all the test cases, use the following command.

::

    $ python -m unittest discover -v tests/

To run a single test, use this following command, replace the test case name
at the end.

::

    $ python -m unittest -v tests.test_api.TestAPI.test_error_unencrypted_reply
