Bistamp Python API
==================

This is an unofficial API library for accessing Bitstamp's REST API.

This version requires Python3.

Sample Usage
------------

Since the project lives only on GitHub, you can install it with::

	pip install git+git://github.com/Pancho/bitstamp.git

In the root folder of this package you can find the file example.py which contains two
examples.

* First example shows how to instantiate the class (with python file format for config)
and how to call the ticker method.

* The second shows how to instantiate the class (with python file format for config) and
how to attach to a web socket


Configuration
-------------

To configure your API key, secret and customer id this library requires for you to use an
external file where you store those two values. To make your life easier, we've made it
possible for you to use one of three file types: json, ini or plain python. To see examples,
browse the examples folder.
Worth mentioning: python config format will work up until Python 3.4 as the importing
procedure is not defined for later versions (expect na update for that case).

Tests
-----

There are 7 TestSuites in the test.py file.

Run with *python -m unittest tests/tests.py*

* TestInstantiation - This suite tests many attempts at instantiating the API client, most of which will fail (and should)
* TestSignature - This suite only tests whether the client class generates a correct signature
* TestUnsignedCalls - This suite actually calls the API and tests whether the client receives the correct responses, but only resources that don't require signatures
* TestSignedValidatedCalls - This suite will test the validations for the signed resource calls and will never arrive to the actual call, as all the tests expect exceptions
