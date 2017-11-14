
#### Ubuntu LTSP Bugs (affecting lubuntu fat clients - no login)

https://bugs.launchpad.net/ubuntu/+source/ltsp/+bug/1330252

Definitively necessary!
pschneider@anschluss.org
2015-02-01: Try to remove `40-ltsp-client` as per this post:

This also affects ltsp fat clients. On fat client environments this bug doesn't occur when /etc/X11/Xsession.d/40-ltsp-client
 is removed from the ltsp chroot.
