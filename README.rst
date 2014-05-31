***************
Caesar Cipher
***************

A Python package and command line script for encoding, decoding and cracking
messages with the `Caesar Shift Cipher`_.

.. image:: https://travis-ci.org/RobSpectre/Caesar-Cipher.svg?branch=master
    :target: https://travis-ci.org/RobSpectre/Caesar-Cipher

.. image:: https://coveralls.io/repos/RobSpectre/Caesar-Cipher/badge.png
    :target: https://coveralls.io/r/RobSpectre/Caesar-Cipher

**Table of Contents**


.. contents::
    :local:
    :depth: 1
    :backlinks: none


============
Features
============

* Encoding
* Decoding
* Cracking (decoding ciphertext without known offset)
* Arbitrary cipher offsets
* Command Line Interface
* Test suite


============
Installation
============

The latest version can be installed via `pip`_.

.. code_block:: bash
    $ pip install caesarcipher

If that doesn't work, give ``easy_install`` a try:

.. code_clock:: bash
    $ easy_install caesarcipher


===========
Usage
===========

------------
Command Line
------------

Encoding a message:

.. code_clock:: bash
    $ caesarcipher --encode "This is a message I want to encode."

Encoding a message with a specific offset:

.. code_clock:: bash
    $ caesarcipher --offset 14 --encode "This is a message I want to encode."

Decoding a ciphertext with a specific offset:

.. code_clock:: bash
    $ caesarcipher --offset 14 --decode "W kobh hc sbqcrs hvwg ghfwbu."

Cracking a ciphertext without knowing the offset:

.. code_block:: bash
    $ caesarcipher --crack "W kobh hc sbqcrs hvwg ghfwbu."


-------------
Library
-------------

Encoding a message:

.. code_clock:: python 
    >>> cipher = CaesarCipher('I want to encode this string')
    >>> cipher.encoded
    'W kobh hc sbqcrs hvwg ghfwbu.'

Encoding a message with a specific offset:

.. code_clock:: python 
    >>> cipher = CaesarCipher('I want to encode this string.',
    ...     offset=14)
    >>> cipher.encoded
    'W kobh hc sbqcrs hvwg ghfwbu.'

Decoding a ciphertext with a specific offset:

.. code_clock:: python 
    >>> cipher = CaesarCipher('W kobh hc sbqcrs hvwg ghfwbu.',
    ...    offset=14)
    >>> cipher.decoded
    'I want to encode this string.'

Cracking a ciphertext without knowing the offset:

.. code_block:: python 
    >>> cipher = CaesarCipher('W kobh hc sbqcrs hvwg ghfwbu.')
    >>> cipher.cracked
    'I want to encode this string.'


#############
Development
#############


----------
Hacking
----------

To hack on the project, clone the `GitHub repo`_:

.. code_block:: bash
    $ git clone https://github.com/RobSpectre/Caesar-Cipher.git

Then install in a `virtualenv`_.

.. code_block:: bash
    $ pip install -e ./


-----------
Tests
-----------

The project uses `Nose`_ for tests.  Simply run from the project root.

.. code_block:: bash
    $ nosetests -v


############
Meta
############

* Written by `Rob Spectre`_
* Used for Hacker Olympics London 2014
* Released under `MIT License`_
* Software is as is - no warranty expressed or implied.
* The `Caesar Shift Cipher`_ is known to be ridiculously easy to crack, as evidenced
  by this very package.  Do not confuse with actual cryptography or use in
  anything that is important - it's just a fun math problem for a sunny vacation
  afternoon.

.. _Caesar Shift Cipher: http://en.wikipedia.org/wiki/Caesar_cipher
.. _pip: http://pip.readthedocs.org/en/latest/
.. _GitHub Repo: https://github.com/RobSpectre/Caesar-Cipher
.. _virtualenv: http://docs.python-guide.org/en/latest/dev/virtualenvs/
.. _Rob Spectre: http://www.brooklynhacker.com
.. _MIT License: http://opensource.org/licenses/MIT