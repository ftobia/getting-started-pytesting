
.. getting started pytesting slides file, created by
   hieroglyph-quickstart on Mon Oct  6 22:53:18 2014.


getting started pytesting
=========================
Frank Tobia


Get the code
------------
- Follow along online:

  - https://github.com/ftobia/getting-started-pytesting/blob/master/index.rst

- Slides:

  - https://github.com/ftobia/getting-started-pytesting/

- Code:

  - https://github.com/ftobia/getting-started-pytesting-code/

- Pytest documentation:

  - http://pytest.org/


Let's get started
-----------------
Clone the code:

.. code-block:: none

  $ git clone https://github.com/ftobia/getting-started-pytesting-code/
  $ cd getting-started-pytesting-code
  $ git checkout beginning

Now we'll make a virtual environment and install pytest.

.. code-block:: none

  $ virtualenv env
  $ source env/bin/activate
  (env)$ pip install pytest


Try running pytest
------------------

Let's try running pytest:

.. code-block:: none

  (env)$ py.test

- We haven't written any tests yet.
- Thus, we expect no tests will run.


What just happened?
-------------------
- Expected:

  - No tests will run.

- Actual:

  - Pytest found and ran a bunch of tests in the virtualenv.

- Solution(s):

  - "Ignore directory" option.
  - Specify test locations explicitly.


"Simplest possible test"
------------------------

- Let's write a simple test.
- What is a test?
- Anything that looks like a test.


Code example: bunch
-------------------

An object that acts like both an object and a dictionary.

Something like:

.. code-block:: python

  >>> foo = Bunch()
  >>> foo['bar'] = 'baz'
  >>> foo.bar
  'baz'

Finished code:

.. code-block:: none

  (env)$ git checkout bunch


Writing some tests for bunch
----------------------------

- Start with simplest possible test.

  - Make sure pytest is set up and our module is importable.

- Then keep writing tests.
- For every case you can think of.


Feature: selecting tests
------------------------
- Run individual tests with the `-k` flag

.. code-block:: none

  (env)$ py.test -k attr -vv
  (env)$ py.test -k del -vv
  (env)$ py.test -k "not attr" -vv


Feature: test fixtures
----------------------
- "A test fixture is something used to consistently test some item, device, or piece of software."

  - Wikipedia

- Set up what a test needs to run.
- Ensure tests are independent.
- Reduce duplication, improve organization.


Code example: chunkify
----------------------
- Given a list of items, and a size,
- return sublists of the given size.

For example:

- Input:

  - [1, 2, 3, 4, 5]
  - 2

- Output:

  - [[1, 2], [3, 4], [5]]

.. nextslide::

Finished code:

.. code-block:: none

  (env)$ git checkout chunkify

Side note:

  - Separate directory for tests.
  - Install our library so it's on PYTHONPATH.

.. code-block:: none

  (env)$ git checkout install
  (env)$ pip install -e .


Feature: exception helper
-------------------------
- Assert that an exception was raised.
- Use the `pytest.raises` context manager.


Feature: parametrization
------------------------
- Run the same test,
- multiple times,
- with different parameters.

  - (inputs, outputs, etc)

- Benefits:

  - Reduce duplication.
  - Improve readability.


Feature: custom markers
-----------------------
- Can "tag" and group tests.
- Run groups of tests separately with `-m` option.
- Change the test run based on markers.

  - e.g. parametrize is a custom marker

Finished code:

.. code-block:: none

  (env)$ git checkout arbitrary-markers


Feature: built-in debugger
--------------------------
- Start debugging at the point an assertion fails.
- `--pdb` command-line flag.
- Actually just pdb, Python's debugger.
- Good talk on pdb:

  - http://pyvideo.org/video/2673/in-depth-pdb


Feature: traceback control
--------------------------
- How much test output do you want to see?
- Command-line flag:

  - `--tb (long/short/line/native/no)`


Code example: is_listy
----------------------
- Does an object "look like" a list?
- For use in code like:

.. code-block:: python

  if not is_listy(x):
    return [x]  # Return a singleton.
  else:
    return x

Finished code:

.. code-block:: none

  (env)$ git checkout is_listy


Feature: parametrized fixtures
------------------------------
- Run a test that includes a fixture multiple times.
- Tests need not be aware of their re-running.


Feature: customizability w/ plugins
-----------------------------------
- Many plugins available.

  - http://pytest.org/latest/plugins.html#extplugins

- "Well-specified hooks" for writing your own.

  - http://pytest.org/latest/plugins.html#well-specified-hooks


Questions?
==========
