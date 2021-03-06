# Changelog

## 1.1

**New features**
* Throw an exception when the CSV source file is not found during extraction.
* Add an optional parameter on the CSV extractor: if set to true it will raise an exception when trying to access non existing columns.
* Add a CSV loader, to be able to ETL from a CSV to another.
* Add the possibility to use multiple extractors and combine them.

**Bufixes**
* Fix an old bug on multilines CSV extraction.
* Fix on ignored discarded rows (only the loader was ignoring them).
* On the ConvertCase transformer : fix to properly handle the change of behavior between PHP 7.2 and 7.3.

**Miscellaneous**
* Improve CI with quality tools (PHPCS, PHPStan...).
* CI: unit tests with PHP 7.2 to 7.4.
* Code cleanup to progressively comply with modern standards.


## Changes for the release 1.0 (the first one since the fork)

* Remove all the old DI system of Laravel (Illuminate):
*   * to make it fully compatible with any PHP Application
    * to remove bad practices and rely only on DI instead of manual instanciation
* Now you have to provide the ETL component instead of calling them with a string
* Added a _setAttributes()_ method to the Row object
* Added a _clearAttributes()_ method to the Row object
* Changed all the namespaces to Wizaplace
* Upgraded to PHPUnit 8
* Fixed tests to remove deprecation to make them compatible with PHPUnit 9
* Added strong typehinting for variables wherever possible
* Added strong typehinting for return type wherever possible
* Switched a lot of method from public visibility to protected
* Using PHPCSFIXER to clean the code
* Validation with PHPSTAN, level 6, however without:
    * checkMissingIterableValueType
    * checkGenericClassInNonGenericObjectType
* Added @TODO warnings where the extract() php function is used. This part will need to be refactored
* Dropped compatibility with PHP < 7.2
