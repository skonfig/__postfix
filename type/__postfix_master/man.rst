cdist-type__postfix_master(7)
=============================

NAME
----
cdist-type__postfix_master - Configure postfix master.cf


DESCRIPTION
-----------
This type can be used to manage Postfix processes configured in the
``master.cf`` file.

See :strong:`master`\ (5) for more information.


REQUIRED PARAMETERS
-------------------
type
   See :strong:`master`\ (5)
command
   See :strong:`master`\ (5)


BOOLEAN PARAMETERS
------------------
noreload
   Don't reload Postfix after changes


OPTIONAL PARAMETERS
-------------------
state
   One of:

   ``present``
      this entry exists in ``master.cf``
   ``absent``
      no entry for this ``--service`` exists in ``master.cf``

   Defaults to: ``present``
service
   See :strong:`master`\ (5)

   Defaults to: ``__object_id``
private
   See :strong:`master`\ (5)
unpriv
   See :strong:`master`\ (5)
chroot
   See :strong:`master`\ (5)
wakeup
   See :strong:`master`\ (5)
maxproc
   See :strong:`master`\ (5)
option
   Pass an option to a service. Same as using ``-o`` in ``master.cf``.

   Can be used multiple times.
comment
   A textual comment to add verbatim with the ``master.cf`` entry.


EXAMPLES
--------

.. code-block:: sh

   # configure a default SMTP service
   __postfix_master smtp \
      --type inet \
      --command smtpd

   # configure an SMTP service using chroot and custom options
   __postfix_master smtp \
      --type inet \
      --chroot y \
      --command smtpd \
      --option smtpd_enforce_tls=yes \
      --option smtpd_sasl_auth_enable=yes \
      --option smtpd_client_restrictions=permit_sasl_authenticated,reject

   # configure a submission service with a comment in the master.cf file
   __postfix_master submission \
      --type inet \
      --command smtpd \
      --comment 'Run alternative smtp on submission port'


SEE ALSO
--------
* :strong:`master`\ (5)


AUTHORS
-------
* Steven Armstrong <steven-cdist--@--armstrong.cc>
* Dennis Camera <dennis.camera--@--riiengineering.ch>


COPYING
-------
Copyright \(C) 2012 Steven Armstrong, 2025 Dennis Camera.
You can redistribute it and/or modify it under the terms of the GNU General
Public License as published by the Free Software Foundation, either version 3 of
the License, or (at your option) any later version.
