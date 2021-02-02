CiviCRM User Mail Check
============================

This module implements error-checking when a CiviCRM user tries to change a
contact's email address that would result in a conflict with another user's
email address.

When someone changes the primary email address for a
CiviCRM contact, CiviCRM updates the `civicrm_uf_match` table and the email
address of the Drupal user account. However, if there is another user account
with that address, Backdrop won't change the email on the user account (because
that would create two user accounts with the same email address), but CiviCRM
does change the contact record and the `civicrm_uf_match` table. That results in
an inconsistency that results in many confusing and hard-to-diagnose problems.
We want to prevent this situation from ever happening, so what we do with this
module is to use CiviCRM's hooks to check and prevent such an email change from
happening.

Installation
------------

- Install this module using [the official Backdrop CMS instructions](https://backdropcms.org/guide/modules).

Documentation
-------------

Additional documentation is located in [the Wiki](https://github.com/backdrop-contrib/civicrm_user_mail_check/wiki/Documentation).

Issues
------

Bugs and feature requests should be reported in [the Issue Queue](https://github.com/backdrop-contrib/civicrm_user_mail_check/issues).

Current Maintainers
-------------------

- [Robert J. Lang](https://github.com/bugfolder)

Credits
-------

- Written for Backdrop CMS by [Robert J. Lang](https://github.com/bugfolder).

License
-------

This project is GPL v2 software.
See the LICENSE.txt file in this directory for complete text.

