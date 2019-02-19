---
title: "Debian"
date: 2019-02-18T22:38:58-08:00
author: maldridge
---

Debian is ancient and its flaws are many, but its still often used in
production.  Why?  Easy: its stable, its old, and its well supported.
The odds are pretty good that almost any software you could want to
run is available in either deb or rpm format.  Debian is where the deb
format comes from so it can usually run it.  Just beware of vendors
that believe debs shipped for Debian and those shipped for Ubuntu are
compatible.

Like buying IBM, running Debian in production is unlikely to get you
fired, unless perhaps you work for IBM or RedHat (an IBM Company).
Its very stable, has a long history of clockwork releases, and has a
good pedigree of developers maintaining it.

If you run Debian in production, there are some things to be aware of:

## APT is very simplistic, sometimes to a fault

Its fairly easy to understand how APT works.  It downloads packages,
it requestes `dpkg` do things with those packages.  The packages will
be fetched via HTTP and will be fetched from whatever mirror the
system is configured to use.

APT doesn't use HTTPS unless you jump through a number of hoops first,
which makes it trivial to host an internal repository.  You can
install additional packages to make APT TLS aware, but given that most
don't even realize you need this to get TLS, its likely most haven't
installed the extra packages.

If you find that the package you want can't be pulled from a repo, you
can always force `dpkg` to just install the raw deb archive.  APT is
wholely unnecessary to install software on the system, its just a
convenience.  You can always drive the underlying systems by hand if
you want to properly shoot yourself in the foot.

## The software is too old to be exciting.

Debian is known for having some of the most out of date software in
the FOSS world.  This is due to the policy of locking versions at a
point release and requiring any further updates for security be
backported to that version.  While some authors do this, many would
prefer you just make a timely upgrade to the current (read:
maintained) version.

You can be sure that if you run Debian in production, your software
will be too old to have any exciting problems in it, so all you'll
need to do is a quick Google search to find any bugs that are known
and how to work around them.  This does though mean that most tooling
will understand how to work with Debian out of the box, and will have
good support for the old versions of software.
