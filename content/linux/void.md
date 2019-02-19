---
title: "Void"
date: 2019-02-18T23:26:56-08:00
author: maldridge
---

Void Linux is a rolling release distribution independently developed
and maintained.  It has a custom derived package manager and uses
LibreSSL and runit.

Void makes it into the LUGStack as a preferred Linux distribution
because of its simplicity and patch frequency.  Void does not modify
upstream sources during packaging, making it easier to take bug
reports to the source.  It also updates very frequently making
security audits a less painful process.  If you need to run user
facing Linux systems, give Void a look due to its excellent desktop
software support, as well as its frequent updates make it ideal for
this purpose.  If you need Linux on your servers, Void is also a fine
choice provided you have a competent ops team available to keep it
rolling along.

Void runs in production in a handful of places, but if you're planning
to follow suit, you should be aware of a few things:

## Poor Enterprise Documentation

Void does have some features that you would expect for use in an
enterprise setting.  It has good support for automatic installation,
but you won't find any documents on this.  If you want to install with
encryption, you'll be writing your own installer to do that and likely
needing to know your stuff on encryption to pull it off.

The IRC community is friendly though, so if you're willing to go and
talk to people, you can get answers to many questions on how to do
professional things with Void.

## Rolling Release == You Must QA

While you can in general get away with not rehearsing upgrades in a
Debian style point release upgrade, you *must* QA your updates in a
rolling release environment.  There's a very good reason that
Microsoft still has patch Tuesday with rolling updates to Windows 10,
and its because skilled ops teams need time to check and approve
updates that might otherwise break important functionality.

## No Commercial Support

If you generally need to have a contract in hand before you launch a
machine, Void is not for you.  It is not possible to get a support
contract for Void, and you are expected to read your own
documentation, understand your own systems, and file your own bugs.
For some this is a deal breaker, but for others it is a major plus,
since it means its impossible to buy changes to the distribution.
