.. index::
    single: Security; Vulnerability Checker

How to Check for Known Security Vulnerabilities in Your Dependencies
====================================================================

When using lots of dependencies in your Symfony projects, some of them may
contain security vulnerabilities. That's why Symfony provides a command called
``security:check`` that checks your ``composer.lock`` file to find any known
security vulnerability in your installed dependencies.

First, install the security checker in your project:

.. code-block:: terminal

    $ composer require sensiolabs/security-checker

Then run this command:

.. code-block:: terminal

    $ php bin/console security:check

A good security practice is to execute this command regularly to be able to
update or replace compromised dependencies as soon as possible. Internally,
this command uses the public `security advisories database`_ published by the
FriendsOfPHP organization.

.. tip::

    The ``security:check`` command terminates with a non-zero exit code if
    any of your dependencies is affected by a known security vulnerability.
    This allows you to add it to your project build process and your continuous
    integration workflows.

.. tip::

    The security checker is also available as an independent console application
    and distributed as a PHAR file so you can use it in any PHP application.
    Check out the `Security Checker repository`_ for more details.

.. _`security advisories database`: https://github.com/FriendsOfPHP/security-advisories
.. _`Security Checker repository`: https://github.com/sensiolabs/security-checker
