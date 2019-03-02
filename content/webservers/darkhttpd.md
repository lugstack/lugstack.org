---
title: "darkhttpd"
date: 2019-03-01T22:16:17-08:00
author: maldridge
---

When all you need is to serve the contents of a directory, darkhttpd
can do that and do it well.  This tiny webserver written in C serves
files at an astonishing rate, and can even make a directory listing
for you.

There's a focus on portability and good engineering which makes this
tiny daemon a good candidate for inclusion here.  Even the notoriously
picky Suckless team says it [sucks less](https://suckless.org/rocks/).

This small size and speedy serving isn't without compromise though:

## No TLS

This is pretty much a deal breaker for serving files to end users.  The
server has no facilities for TLS or any other such features, so you'd
need to put it behind a load balancer or similar device to terminate
the connection.

## No Configuration Files

All configuration is done by flags.  Not that there's much
configuration to make - effectively only the webroot - but it does
mean that however you choose to start darkhttpd must be aware of all
of its configuration data and requirements.

## No CGI / Reverse Proxy

If you were hoping to have a tiny front-end that could be bolted onto a
larger CGI server, you'll have to keep looking.  The mission and goals
for darkhttpd are very clear, and that is to serve static files.
