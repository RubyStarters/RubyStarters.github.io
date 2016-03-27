---
layout: post
title:  "Ruby On Rails USB installation"
date:   2016-03-22 22:16:17 +0100
categories: installation
---
It's been a long time since the last post, but we are happy to announce and
interesting, maybe even new approach to install a full Ruby On Rails development
environment, that works consistently on lot's of hardware.

Origin for this project was a frustrating installation experience of the
Railsinstaller on older hardware. We tried out a docker approach as well in
another Rails starters session, but we didn't have to much success with that
as well.

The next idea was creating a standardized environment. The approach to implement
it a virtual machine introduced Virtualbox or a different hypervisor as an
additional dependency. Furthermore the is the expected performance loss from
the additional abstraction layer.

But we didn't give up and switched gears once more. This time we started installing
a Linux live system on a decent fast USB stick. This approach seemed to show
first successes, but we suffered another setback: Macbooks didn't like the
stick and refused to boot from it. We were quite close to giving up, when a
last promising idea came to our minds:
Why not install Linux on a USB stick as if it were a full blown hard disk. Current
USB sticks always managed to max out the capabilities of all of our USB controllers
speed-wise. A USB stick reached a write speed of 70MBs per second, comparable
to current spinning hard disks.

While it is quite easy to install Ubuntu Mate on a USB stick, there is still
quite a lot to do for a full blown development machine: We want to see
Ruby, Ruby On Rails, the database management system PostgresQL, an Apache webserver,
a decent editor (Atom.io, if possible). A nice addon would be to get offline
documentation working. To make a long story short: We succeeded by the simple
means of writing a [bash script](https://github.com/RubyStarters/Ideas/blob/master/bootstrap).   

Stefan aka [@informatom](https://twitter.com/informatom)
