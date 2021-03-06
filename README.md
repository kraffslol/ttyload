Home page: http://www.daveltd.com/src/util/ttyload/
GitHub:    https://github.com/lindes/ttyload/

## INTRODUCTION

Hi there,

This is ttyload.  It was originally inspired several years ago
when I (David Lindes, the original author) found myself with a
desire to track load averages over time on a UNIX(ish) machine
that I didn't have a way to run xload on (or any X application
actually -- it didn't have the libraries installed, and it was
not a reasonable choice to change that for that machine)...  I
figured this concept might come in handy in a variety of other
situations, such as when logged in on a non-graphical console,
or logging in remotely without an ability to forward X, etc...

So, I wrote it.  Now, when I originally wrote it, I was pretty
inexperienced, so, while I new about curses, and that it would
be nice to have this utility written with it, I didn't feel up
to figuring it out and making that go, so I just used the fact
that I happened to know a few ANSI escape sequences, and faked
it as best I could at that time.  Since then, I've found that,
indeed, this functionality does have times when it's useful...
And I know of no other utilities that perform quite this task.

For a while, I only needed it on one platform, and so I simply
recompiled it from time to time as I moved from one machine to
another.  But, eventually, I stopped having such a homogeneous
environment, and wanted it for other platforms.  And different
platforms required different methods of getting data about the
load averages...  For a while, I didn't feel quite enough of a
desire to have it elsewhere to make it work.  But eventually I
was convinced, through both my own desire and some urging from
my friend Vern, to dust off the code and make it work again...

So that's what I did.  In doing so, I tried to make any purely
new code be written in ways that would allow easy expansion of
things onto new platforms, and generally to do things cleanly.
But at the same time, the only feature I wanted to add was the
ability to run it elsewhere, so, as it happens, there is still
quite a bit of a primitive flavor to this program.  But it did
manage to get built on Linux, and now even a couple of others,
so now I'm going ahead and making it available to the world...

Please consider ttyload as "beta" (or maybe even only "alpha")
quality software, and assume no guarantees whatsoever, thanks.

For info on how to provide whatever feedback, or to get future
versions as they become available, point your browser towards:

	http://www.daveltd.com/src/util/ttyload/

Thanks,

David Lindes

## PLATFORMS...

ttyload has been shown to run on systems running, at least:

- Linux (at least some configs of it -- I'm using a SuSE 6.x box
  to build it on, with a 2.2.x kernel)
- IRIX 6.5 (and possibly other versions?)
- FreeBSD (some version or other, I'm not familiar with their
  numbering system...  4.4, I think.)
- Solaris 2.x and later (at least 2.6 and 8)
- Isilon OneFS

Feel free, if you like, to submit patches to add more platforms
(or other versions of existing platforms), and please let me
know also if it runs unmodified on any other platforms.

## INSTALLATION

to build ttyload, in theory all you need to is type 'make'.  If
you want to also install it, 'make install' should do the trick,
which will copy it to /usr/local/bin (or another directory if
you edit the INSTALLDIR setting in the Makefile or do
'make install INSTALLDIR=whatever').

## RUN-TIME FOO

After building, you can run ttyload with './ttyload' (or just
'ttyload' if either '.' is in your $PATH, or you did the make
install into a directory that is), which will start up ttyload.
What you see is basically a screen with three graphs on it.  One
is for the 1-minute load average, one for the 5min, and one for
the 15min.  Assuming you have color support, these will be red,
green, and blue, respectively, and if they overlap, RGB addition
will be done on them...  Red + Green == Yellow, etc.  See the
Legend in the lower-left hand corner for the cheat-sheet.
(Note: all my color naming is assuming your terminal is
"reasonably standard" -- and no, I don't know exactly what
"reasonably standard" means, so don't ask.  ;-)

To exit, type <ctrl-C> (hold down the "control" or "ctrl" key,
and then simultaneously press the "c" key), or whatever you have
'stty intr' set to.  If and when I have a curses mode,
presumably 'q' and/or '<esc>' will work too.

## OTHER THINGS

- ttyload -h gives you usage info.

- the 'loader' program is generally something you don't want to run.
  In case you're curious, it's a "load bomb" which is specifically
  designed to increase your load average, but in a relatively limited
  way.  This was done so that testing and screen shots and whatnot would
  be easier, and I don't expect folks to run it normally, but I figured
  I'd provide it anyway, just in case you're having a "Spinal Tap"
  moment or something.  ;-)

- there's a todo list on the web page, if you're thinking of a feature
  you want to see added, check there first before requesting it.

- Please see the LICENSE file for information on what you're allowed to
  do with ttyload, etc.  It's not under the GPL or some other license
  because I'm not entirely happy with most of those licenses.  I
  eventually hope to put it under the GratuityWare Public License
  (GWPL, see http://www.gratuityware.org/), but that doesn't exist yet,
  because I haven't written it yet, so, that's yet to come.

- Despite the lack of existence as yet of the GWPL, I do consider
  ttyload to be GratuityWare.  This means that there will never be a
  required fee for using it, but donations are encouraged.  See the web
  site (listed above at the end of the INTRODUCTION section) for a link
  that will allow you to do that.  Or send me e-mail if you don't want
  to use the available method(s), but do want to contribute, and we can
  work something out.

- Send any other feedback (comments, requests, bug reports, etc.) to me
  at <src/ttyload@daveltd.com> (yes, '/' is valid in an e-mail address!
  If your mailer can't hack it, though, you can substitute '-' for it,
  if you must).

- Feel free to
  [![Flattr this project](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=lindes&url=https://github.com/lindes/ttyload&title=ttyload&tags=github&category=software),
  if you find it useful.  Your support would be appreciated.  :)
