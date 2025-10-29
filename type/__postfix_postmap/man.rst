cdist-type__postfix_postmap(7)
==============================

NAME
----
cdist-type__postfix_postmap - Run postmap on the given file


DESCRIPTION
-----------
This type will run the postmap command on the file specified in the
``__object_id``.

**NB:** this type makes no checks. It will execute postmap unconditionally, on
 every skonfig run!


EXAMPLES
--------

.. code-block:: sh

   __postfix_postmap /etc/postfix/generic


AUTHORS
-------
* Steven Armstrong <steven-cdist--@--armstrong.cc>


COPYING
-------
Copyright \(C) 2012 Steven Armstrong.
You can redistribute it and/or modify it under the terms of the GNU General
Public License as published by the Free Software Foundation, either version 3 of
the License, or (at your option) any later version.
