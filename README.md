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

## Jenkins configuration

Create a Jenkins ``freestyle`` project. Now in your Jenkins home directory, replace the ``config.xml`` with the contained ``jenkins-config.xml``, reload the configuration and adjust the build settings to your liking. Done.

If executed manually, you can execute the ``build-parallel`` goal (``ant build-parallel``).

## TeamCity integration

TeamCity supports autoconfiguration via stdout to gather build artifacts and display them properly. To be done.
