---
title: "Alpine"
date: 2019-03-01T21:53:44-08:00
author: maldridge
---

Alpine is a point released distribution independently developed and
maintained.  It has a custom package manager and is notable for being
incredibly compact with a BusyBox base system and the exclusive use of
musl-c.  Alpine uses openrc as the preferred init and has a focus on
extreme minimalism.

Alpine makes it into the LUGStack as a preferred Linux distribution
because of its minimalism and speed.  Alpine is a fine choice for the
base of a container image as well as a solid choice for the operating
system "on the metal" in a larger cluster.

Alpine has an excellent security track record making it a reasonable
challenger to Debian's security team both in quality and throughput.
If you're working with a team that's bent on using docker or whatever
is the container engine of the week, strongly consider Alpine as the
base of your images for speed, size, and security.

Of course the LUGStack doesn't just look at the positives, Alpine has
some gotchas that should be called out before you jump in:

## Very Slow IRC Channel

If you need to find out why something's gone wrong on Alpine, you may
reach out on the IRC channel where you can reliably reach the entire
development team of the distribution, but you should be aware that the
channel is very slow, so be prepared to idle overnight.  The good news
is that the channel is extremely knowledgeable and knows a lot about
the known defects in Alpine.

## No Commercial Support

Similar to other distributions in this size class, there is no
commercial support for Alpine.  If you have a management department
that believes that they need a contract for everything, Alpine
probably isn't for you, but then again containers and modern
infrastructure probably aren't either.

## No GNU C Library

While the musl C library is a fantastic project and really goes to
show just how much software is incorrectly using internal GNU headers,
it does come with some compatibility problems.  If you need to run
proprietary, binary only software, you may run into problems on
Alpine.  The distribution provides a library for some compatibility,
but there are limits to what the library can do, and so for software
you can't get source for, its sometimes easier to just have GNU C
libraries available.
