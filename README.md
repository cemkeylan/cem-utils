cem-utils
=========

These are some utilities that are not much
use to anyone, but I use for my own. Most of
them are just simpler re-implementations of 
programs that are pretty unnecessary for most
people. If i published them standalone, lots
of people would get mad at me for just modifying
some program that they like with really small
changes.

I really don't care about what you think about
these. I just use them.

Here are some explanations per utility. Right now
there is only one but I will be publishing others.


nap
---

Literally Leah's zzz[1] with only suspend feature.
It is compatible with zzz so it can read zzz.d
Why don't I add hybernation stuff? Because my
computer cannot hybernate.

You see my point? I don't have a use for more 
than half of the things zzz script does. So
I deleted them.

To install run, as root if necessary

    make -C nap install

This will create the /etc/zzz.d directories and
install nap


nap-hooks
---------

POSIX-compliant and simplified zzz-user-hooks[2]. 
Does not support Wayland. Works with sbase-ubase.
Is a shell script instead of a bash script. 32
lines of shell code instead of 112.

To install run, as root if necessary

    make -C nap-hooks install

This will create /etc/zzz.d/resume/99-onresume and
/etc/zzz.d/suspend/99-onsuspend

You can add user hooks to ~/.onsuspend and
~/.onresume to get them working.

[1]: http://git.vuxu.org/runit-void/tree/zzz
[2]: https://github.com/bahamas10/zzz-user-hooks
