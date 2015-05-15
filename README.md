# External Authentication Module

## Requirements

* Silverstripe 3.1.0 or later
* Some PHP modules depending on the driver used like php-imap, php-ldap or
  some specific PEAR and/or PECL modules. The module requirements are
  documented in the configuration template for that module (see doc directory)


## Documentation

<https://web.archive.org/web/20090421092632/http://doc.silverstripe.com/doku.php?id=modules:external-authentication> (obsolete)


## Installation Instructions

* `composer require lancer/silverstripe-auth-external`
* run /dev/build  (like http://www.example.com/dev/build)

You should now have an "External Account" tab on the admin page.

If things didn't work as expected, enable the debugging in the config file.
The resulting log should point out the configuration mistakes.

Next to the divers included in the official release, some (user maintained)
drivers may be available by visiting the documentation link above.


## Usage Overview

This module enables you to use external authentication sources for password
verification. At the moment this module has 4 drivers. LDAP, FTP, IMAP and
HTTPBASIC. The IMAP driver also supports POP3. All drivers support SSL. TLS
is only supported by the LDAP and IMAP drivers.

When you use this module you will still need to create accounts within
SilverStripe. There will be two extra fields for each account, specifying the
username and the external authentication source it comes from.

If you run your website at your ISP which also hosts your mailbox, you can use
the ISP's IMAP/POP3 server to validate your logon. Other users at the ISP
cannot login when you do that because the accounts also need to be registered
within SilverStripe.
