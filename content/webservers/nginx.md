---
title: "Nginx"
date: 2019-03-01T22:23:35-08:00
author: maldridge
---

Nginx is a battle hardened webserver that is famous for being one of
the first viable servers to solve the C10K challenge.  Over the years
its become a staple of production environments and can often be found
hard at work serving both production and internal workloads.

Nginx is capable of handling both static and dynamic content and
speaks most proxy protocols in use today.  The configuration file is a
clear, readable syntax and is generally easy to work with.  By default
the server follows the conf.d pattern to load configuration meaning it
plays well with most configuration management solutions.

Nginx is a fine default choice, but like all software it has good
reasons to be disliked:

## Nginx Plus

Nginx Plus is a commercial offering built on top of Nginx.  Like many
other non-RedHat companies that have tried to figure out how to make
money on Open Source, this means there's a split between what you get
for free, and what you have to pay for here.  In this case, one of the
biggest features you don't get in the free version are good metrics.
Given that the world is increasingly trending towards metrics as the
ideal way to make technical decisions, this can be very frustrating
when working with Nginx.

## Not Really Modular

Nginx is really a monolith in disguise.  Depending on if you have
Nginx Plus or not, you may have better module support than is
available in the base version, but its still nowhere near other older
webservers in terms of modules available or capabilities provided by
modules.
