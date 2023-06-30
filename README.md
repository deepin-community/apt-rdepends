apt-rdepends
------------

This is a useful little program that does recursive dependency lookups.
Now, apt-cache can already do this with its --recursive switch; but
it doesn't know how to recursively look backwards into the dependency list.

	Why is this useful?  Let us say you wish to modify a library,
like libfoo2 so that it uses versioned symbols.  Now you want to find out
which programs depend on libfoo2.  But what if libraries depend on
libfoo2, then what depends on them?  Et cetera, et cetera.  It was just
this case with libstdc++* that prompted me to write this program.

	There are some things that apt-rdepends cannot do.  It does not
yet know how to look at source dependencies, but this should be fixed
once libapt-pkg-perl exposes the correct interface.  For now, you should
use grep-dctrl on the /var/lib/apt/lists/*Sources files to deal with
this.

	Happy hacking.

-- Simon Law  <sfllaw@debian.org>  18 Aug 2002 09:13:10 -0400
