The released source packages of recent versions of PuTTYcyg (from 2007 and later) is released as a gzipped patch file.  The patch file itself is actually a perl script which can automagically download the [PuTTY source](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html), patch it, and build PuTTYcyg (putty.exe and cthelper.exe).  Building it requires Cygwin with make, gcc-mingw, perl, and patch installed.  If you're feeling lucky:

```
zcat putty-0.60-cygterm-20090811.patch.gz | perl
```

If you're building from the repository, instead use these commands from the `putty-0.60` directory:

```
perl mkfiles.pl
make -C windows -f Makefile.cyg putty.exe
make -C windows/cthelper
```

Note that this creates a debug build (this is PuTTY's default).  To create a release build, see Makefile.maint.