SECSI Email Command-line Script I
=====

SECSI is a script that allows one-liners for secure IMAP access to secure IMAP providers, e.g. GMail. The only dependencies are bash and openssl, both of which are included in OS X and many *nix distros.

Outputs what the IMAP server returns, so it isn't pretty.

### Config

Set the following env vars:

* `IMAP_SERVER=imap.example.com:993`
* `IMAP_USER=youremail@example.com`

Optionally, you can set these:

* `IMAP_DELAY=2` (default is 2 seconds)
* `IMAP_S_CLIENT_OPTS="-crlf -starttls smtp"` (default is `-crlf`)

### Usage

Example usage:

```
secsi list
secsi fetch mailbox id_or_range *options
  e.g.
  secsi fetch INBOX 3456 FULL
  secsi fetch INBOX 3456:3466 \"(BODY.PEEK[HEADER.FIELDS (DATE FROM SUBJECT)])\"
secsi search mailbox *options
  e.g
  secsi search INBOX SENTON 1-jun-2012
  secsi search INBOX SENTSINCE 1-may-2012 SENTBEFORE 3-jun-2012
secsi expunge INBOX
```

Read [RFC 3501](http://tools.ietf.org/html/rfc3501).

### License

Copyright 2014 Gary S. Weaver, released under the [GPL v3][lic] license.

[lic]: http://github.com/garysweaver/email_cli/blob/master/LICENSE
