---
layout: post
title:  "Ruby On Rails USB Stick Installation"
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

The script is not only idempotent (it doesn't cause any issues to run it
several times). It further more creates a bash alias @update@ and it introduces
an update for all components installed. - If we will improve the script in
future days, you will receive the latest version with the next run of *update*.

We introduced several additional gimmicks: Sonic Pi gets installed as wall as
the new programming language Crystal, that is quite close to Ruby syntax-wise,
but in contrast to Ruby it is a compiled and therefore faster language. Keep
in mind, though, that Crystal is not yet production ready.

To be on the safe side (we install services with the database management system
and the web server), we enable the uncomplicated firewall in standard configuration.
That means, that all outgoing traffic is still allowed (you probably want to
reach external documentation sources), but incoming traffic is blocked.

Lot's of additional libraries are installed, to be able to compile several modules
in our prefered gems, e.g. to access the database from our Rails applications.

Please read the [bash script](https://github.com/RubyStarters/Ideas/blob/master/bootstrap)
yourself, it's pretty much self explaining and heavily commented, even for bash
scripting newbies.

Ruby is installed in three different versions (2.1, 2.2 and 2.3) to be compatible
to almost all Rails tutorials avaliable out there. We installed different Rails
versions alongside (latest Rails 3.2 with Ruby 2.1; latest Rails 4.2 with Ruby 2.2
and latest Rails 5 with Ruby 2.3).

To be able to handle file uploads in our Rals applications we install Paperclip,
for authentication, we install the famous Devise gem.7

For testing purposes we install Chromium browser alongside Firefox.

We installed - and that's the last Gimmick - the offline documentation browser
Zeal with offline docs for all our relevant programming languages and tools
with a [second script](https://github.com/RubyStarters/Ideas/blob/master/zeal-docsets).
This way documentation for Ruby, Ruby On Rails, Bash, HTML, CSS, SQLite, MySQL, PostgresQL,
the Twitter Bootstrap CSS framework, Coffeescript, HAML, Jekyll, Less, Apache,
Markdown, Sass, Font Awesome, Zurb Foundation and semantic UI.

Please give it a try and give feedback. And if you have fun, please talk and
write about it.

Stefan aka [@informatom](https://twitter.com/informatom)
