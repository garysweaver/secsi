SECSI Email Command-line Script I
=====

SECSI is a script that allows one-liners for secure IMAP access to secure IMAP providers, e.g. GMail. The only dependencies are bash and openssl, both of which are included in OS X and many *nix distros.

Outputs what the IMAP server returns, so it isn't pretty.

### Config

Set the following env vars:

* `IMAP_SERVER=imap.example.com:993`
* `IMAP_USER=youremail@example.com`

### Usage

Refer to [rfc3501](http://tools.ietf.org/html/rfc3501) for search.

Example usage:

```
secsi list
secsi get mailbox id_or_range
  e.g.
  secsi get INBOX 3456
  secsi get INBOX 3456:3466
secsi search mailbox search_string
  e.g
  secsi search INBOX SENTON 1-jun-2012
  secsi search INBOX SENTSINCE 1-may-2012 SENTBEFORE 3-jun-2012
secsi expunge INBOX
```

### License

Copyright 2014 Gary S. Weaver, released under the [GPL v3][lic] license.

[lic]: http://github.com/garysweaver/email_cli/blob/master/LICENSE
