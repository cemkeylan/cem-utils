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
there this is not a big repository, but I will be
publishing other utilities, once I sort everything
out.

Not all of my utilities are here at the moment. Some
are on my main computer that I cannot reach at the
moment. Some live on my dotfiles (I will be updating
my dotfiles for Carbs Linux someday I promise). I will
also be merging my useless utilities that are currently 
on individual repositories here.

Below are explanations per utility and here is the
small list of programs:


* nap
* nap-hooks
* dwm-notify-send
* pm


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


dwm-notify-send
---------------

A simple notify-send command to use dwm's bar for
displaying notification. It must work with every bar
that uses the WMNAME function, but I have only tested
it on dwm bar.

The delimiter ('-' by default) can be edited from the
`NOTIFY_SEND_DELIMETER` environment variable. This way
you can also make use of the second bar, if it exists.

**Dependencies**

* A bar with WMNAME function.
* xsetroot
* getopt
* timeout
* POSIX sh

To install run, as root if necessary

    make -C dwm-notify-send install

This will install `notify-send` and `kill-notification`
to `/usr/local/bin`


pm
--

Dumb password manager with absolutely no fancy features. By
that I mean,

* No password generation
* No git integration
* No questions asked
* No grepping/finding passwords
* No clipboard support
* No tree view
* Does not ask for password input (reads from stdin)

Currently less than 35 LOC. Supports adding/deleting/listing/showing
passwords. I don't intend on implementing any more features.
You can wrap this script with something other to make use of
it. 

To install run, as root if necessary

    make -C pm install

You really do think that asking for password for twice blah
blah is a really important feature? Okay, then add a function
to your shellrc/profile like this.

    pmask() {
        [ "$1" ] || return 1
        printf 'Enter your password: '
	read pass
	printf 'Enter your password again: '
	read pass2
	if [ "$pass" = "$pass2" ] ; then
	    printf '%s' "$pass" | pm a "$1"
        else
	    printf "Passwords don't match\n"
	    return 1
	fi
    }

You want to copy to clipboard? That's easy! You just need
to do a `pm s passname | xclip -sel c`. You can still make
it a function by doing this

    copypass() {
        [ "$1" ] || return 1
	pm s "$1" | xclip -sel c
    }

The whole rationale is that you can already do that with simple
commands. Why complicate (and possibly break) things by introducing
them into a single script? If you want some function that is
a must for you, implement it yourself with some script or
a shell function. This way, it works just as you intended it.


[1]: http://git.vuxu.org/runit-void/tree/zzz
[2]: https://github.com/bahamas10/zzz-user-hooks
