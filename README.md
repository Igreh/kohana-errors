kohana-errors
=============

Simple module for handling errors in Kohana 3.2

Description
-----------
The Error module allows customization of error handling by overriding Kohana's default exception handler. 
The module starts to "work" only if not DEVELOPMENT environment is set, otherwise
kohana native handler "works".  
By default - there are two predefined views for 404 and 500 errors. You can use your own views by adding files
to `APPPATH.'/views/errors/'` folder. Each view must be named according to the error code it represents (i.e. 404.php,
500.php etc). Errors without defined views are handled as 404 error.  
For AJAX and CLI - output is just "ERROR" message.
You can throw exceptions in your code:

```php
    throw new HTTP_Exception_404;
```

Installation
------------

* Install module.
* Add the following lines to bootstrap.php before the call to Kohana::init()

```php
    // Force loading module's Kohana_Exception class
    require MODPATH.'errors/classes/kohana/exception'.EXT;
```