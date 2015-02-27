# A TYPO3 QA template

This is a skeleton for TYPO3 extensions which contains a ant build script that executes a bunch of goals that contain the following metrics / test utilities:

* PHP Syntax checking (linting)
* PHPUnit (config in [phpunit.xml.dist](phpunit.xml.dist))
* PHPMD - PHP Mess Detector (config in [phpmd.xml](phpmd.xml))
* PHPCS - Code style check (config in [phpcs.xml](phpcs.xml))
* PHPCPD - Copy and paste detection
* PHPDox - API Doc generator (enriched with git build data, phpcs, phpmd, coverage etc..) (config in [phpdox.xml](phpdox.xml))

## Execution

You need to install the ``ant`` build tool (which in turn requires Java).

* Clone the reposository ``https://github.com/cedricziel/typo3-extension-qa-skeleton.git``
* Install composer dependencies ``composer install``
* Execute the build ``ant build``

## A word on error handling

Errors are handled gracefully. What this basically means, is that you would need to adjust the ant file [build.xml](build.xml)
to stop the build upon an error. Unless you add ``failonerror="1"`` to one of the ``exec`` directives, the build will always pass.

## Jenkins configuration

Create a Jenkins ``freestyle`` project. Now in your Jenkins home directory, replace the ``config.xml`` with the contained ``jenkins-config.xml``, reload the configuration and adjust the build settings to your liking. Done.

If executed manually, you can execute the ``build-parallel`` goal (``ant build-parallel``).

## TeamCity integration

TeamCity supports autoconfiguration via stdout to gather build artifacts and display them properly. To be done.

## License

The configuration itself is licensed under the MIT license.
The sample Code in Classes && Test folders is tainted by the GPL license.

### The MIT License (MIT)

Copyright (c) 2014 Cedric Ziel <cedric@cedric-ziel.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
