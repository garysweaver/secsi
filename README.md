SECSI Email Command-line Script I
=====

SECSI is a script that allows one-liners for secure IMAP access to secure IMAP providers, e.g. GMail. The only dependencies are bash and openssl, both of which are included in OS X and many *nix distros.

Outputs what the IMAP server returns, so it isn't pretty.

### Config

Set the following env vars:

* `IMAP_SERVER=imap.example.com:993`
* `IMAP_USER=youremail@example.com`

### Usage

```
  secsi list
  secsi get mailbox id_or_range
    e.g.
    secsi get INBOX 3456
    secsi get INBOX 3456:3466
  secsi senton mailbox date
    e.g
    secsi senton INBOX 1-jun-2012
```

### Raw IMAP Access via OpenSSL

You don't need this to interact directly with IMAP. For example:

    openssl s_client -connect imap.googlemail.com:993 -crlf

and then (`t1` command tag is arbitrary):

    t1 LOGIN someuser@gmail.com somepassword

Will get you in, and then you can get familiar with IMAP [here](http://tools.ietf.org/html/rfc3501).


### Contribute

Pull requests welcome to add additional support for IMAP commands and configuration, SMTP, etc.

### License

Copyright 2014 Gary S. Weaver, released under the [GPLv3][lic] license.

[lic]: http://github.com/garysweaver/email_cli/blob/master/LICENSE
