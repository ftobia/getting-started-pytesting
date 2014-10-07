
.. getting started pytesting slides file, created by
   hieroglyph-quickstart on Mon Oct  6 22:53:18 2014.


getting started pytesting
=========================


Pytest features
---------------
- assertions using built-in `assert` statement
- helpful tracebacks
- fixtures
- parametrization
- "slice and dice" your test suites
- built-in debugger


Let's get started
-----------------
First let's check out my git repo (for later):

.. code-block:: none

  $ git clone git@github.com:ftobia/{franks-cool-repo}.git
  $ cd {franks-cool-repo}
  $ git checkout tag-1

Now we'll make a virtual environment and install pytest.

.. code-block:: none

  $ virtualenv env
  $ source env/bin/activate
  (env)$ pip install pytest
  (env)$ py.test


What just happened?
-------------------
- Expected:

  - no tests run

- Actual:

  - pytest found and ran a bunch of tests in the virtualenv

- Solution:

  - "ignore directory" option


(Look at the fancy output)
--------------------------

Let's write some actual code
----------------------------
.. code-block:: none

  (env)$ git checkout -f tag-3

- Simplest possible test.
- Expected:

  - pytest is set up properly
  - our module is importable


First, write a failing test
---------------------------
.. code-block:: none

  (env)$ git checkout -f tag-4

- "Test-Driven Development (TDD)"


Then, make the test pass
------------------------
.. code-block:: none

  (env)$ git checkout -f tag-5

- "Red / green refactoring"


Rinse, repeat
-------------
- Write code to make the test fail
- Write enough code to make it pass

.. code-block:: none

  (env)$ git checkout -f tag-6  # Fail.
  (env)$ git checkout -f tag-7  # Pass.


Keep writing tests
------------------
- Let's make it possible to "complete" todo items
- Failing test, again:

.. code-block:: none

  (env)$ git checkout -f tag-8

- Simplest thing to make it pass, again:

.. code-block:: none

  (env)$ git checkout -f tag-9


Aside: selecting tests
----------------------
- Run individual tests with the `-k` flag

.. code-block:: none

  (env)$ py.test -k add_item -vv
  (env)$ py.test -k add -vv
  (env)$ py.test -k complete -vv
  (env)$ py.test -k "not add" -vv


New feature: completed items
----------------------------
- Let's keep track of completed items
- Failing test:

.. code-block:: none

  (env)$ git checkout -f tag-10

- A test should test one thing
- Note the code duplication
- Note the test similarity
- We'll fix that in a minute


New feature: completed items
----------------------------
- Make them pass

.. code-block:: none

  (env)$ git checkout -f tag-11

- Now let's work on our tests some more


More tests
----------
- Write a few more tests

  - (these ones will pass)

.. code-block:: none

  (env)$ git checkout -f tag-12

- What to do about the duplication?
- Two tools:

  - Fixtures
  - Parametrization


Fixtures
--------
- Set up / tear down
- Ensure a particular state
- Ensure a resource

  - If it's shared, make sure it's clean

First try:

.. code-block:: none

  (env)$ git checkout -f tag-13

Second try:

.. code-block:: none

  (env)$ git checkout -f tag-14


Parametrization
---------------
- Run a test multiple times w/ multiple parameters
- Greatly reduces code duplication
- Tests are easier to read
- Success / failure reporting is maintained

.. code-block:: none

  (env)$ git checkout -f tag-15

Contrived example:

.. code-block:: none

  (env)$ git checkout -f tag-16


Custom markers
--------------
- Can "tag" and group tests
- Run them separately
- Or change the test run based on them (e.g. parametrize)

.. code-block:: none

  (env)$ git checkout -f tag-17


Other cool stuff
----------------
- debugger

  - `--pdb`

- traceback control

  - `--tb (long/short/line/native/no)`

- lots of extensions / plugins
- works w/ unittest.TestCase


Questions?
==========

