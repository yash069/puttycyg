PuTTYcyg 20071202 fixes a terminal window resizing bug reported by Stefano Bacelle and fixes the missing "meta-bit" configuration option reported by Christian Roche.

PuTTYcyg 20071012 fixes some build issues and hopes to be more responsive.

PuTTYcyg 20071011 upgrades to PuTTY 0.60.

PuTTYcyg 20071009 fixes a memory allocation error reported by Minjang Kim and adds multiple monitor support (again).

PuTTYcyg 20070320 fixes an issue when saving a configuration; the command name setting is no longer saved as part of the "Default Settings" configuration.

PuTTYcyg 20070207 fixes build problems when using MSVC. It also contains cygterm-enabled versions of both putty.exe and puttytel.exe. This version incorrectly reports its version as "PuTTYcyg 0.59" instead of "PuTTYcyg 20070207".

PuTTYcyg 20070205 upgrades to PuTTY 0.59.

PuTTYcyg 20060525 fixes a command line processing bug which should have never made it out into release.

PuTTYcyg 20060405 is compiled with support for multiple monitors.

PuTTYcyg 20051212 upgrades to PuTTY 0.58. Also puttycyg.exe is now simply putty.exe.

PuTTYcyg 20050910 fixes a bug in command line processing when the default protocol is not 'cygterm'.

PuTTYcyg 20050804 adds the [meta-bit patch](http://www.chiark.greenend.org.uk/~sgtatham/putty/wishlist/meta-bit.html) as well as improved select() handling for slightly improved response.

PuTTYcyg 20050330 fixes some select()-related bugs.

Versions of PuTTYcyg prior to 20041215 are affected by this [vulnerability](http://www.chiark.greenend.org.uk/~sgtatham/putty/wishlist/vuln-ssh2-debug.html). Versions of PuTTYcyg prior to 20040811 are affected by the [vulnerability](http://www.coresecurity.com/common/showdoc.php?idx=417&idxseccion=10) discovered by Core Security Technologies. You are advised to upgrade to the latest version of PuTTYcyg, especially if you are using PuTTYcyg as an SSH client.

Versions of PuTTYcyg prior to 20040811 were based on source in the PuTTY CVS tree. Version 20040811 is based on PuTTY 0.55. Future versions will be based on PuTTY release versions (0.55 and up) instead of CVS and will be labeled according to the version of PuTTY on which they are based.