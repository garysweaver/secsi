SECSI Email Command-line Script I
=====

SECSI is a script that allows one-liners for secure IMAP access to secure IMAP providers, e.g. GMail. The only dependencies are bash and openssl, both of which are included in OS X and many *nix distros.

Outputs what the IMAP server returns, so it isn't pretty.

### Config

Set the following env vars:

* `IMAP_SERVER=imap.example.com:993`
* `IMAP_USER=youremail@example.com`

Optionally, you can set these:

* `IMAP_S_CLIENT_OPTS="-crlf -starttls smtp"` (default is `-crlf`)

### Usage

Example usage:

```
  export IMAP_SERVER=imap.example.com:993
  export IMAP_USER=youremail@example.com
  ./secsi LIST '"" "%"'
  IMAP_MAILBOX=INBOX ./secsi FETCH 3456 FULL
  IMAP_MAILBOX=INBOX ./secsi FETCH 3456:3466 "(BODY.PEEK[HEADER.FIELDS (DATE FROM SUBJECT)])"
  IMAP_MAILBOX=INBOX ./secsi SEARCH SENTON 1-jun-2012
  IMAP_MAILBOX=INBOX ./secsi SEARCH SENTSINCE 1-may-2012 SENTBEFORE 3-jun-2012
```

Read [RFC 3501](http://tools.ietf.org/html/rfc3501).

### License

Copyright 2014 Gary S. Weaver, released under the [GPL v3][lic] license.

[lic]: http://github.com/garysweaver/email_cli/blob/master/LICENSE
