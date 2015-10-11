## How do I make a shortcut to run PuTTYcyg? ##
Use this command line (_Target:_)
```
C:\path\to\putty.exe -cygterm -
```
or use a saved session, e.g.:
```
C:\path\to\putty.exe -load Local
```
Optional: set the working directory (_Start in:_) to your Cygwin installation's `/bin` directory: e.g.:
```
C:\Cygwin-1.7\bin
```
As of PuTTYcyg version 20090508, setting the working directory will allow you to turn off the _Autodetect Cygwin Installation_ and use multiple Cygwin installations on your system.

The [PuTTY documentation](http://the.earth.li/~sgtatham/putty/docs.html) has more information about how to use sessions.

## I have a non-Cygwin program which doesn't work under certain circumstances.  What's wrong? ##
PuTTYcyg is not a Windows console replacement program, it is a local terminal emulator for Cygwin programs and therefore is only meant to work with Cygwin programs.  _Some_ Windows console programs will work _most_ of the time.  However, since PuTTYcyg does not provide a Windows console device, these console programs will break as soon as they try to access it (for example by trying to change the `ENABLE_ECHO_INPUT` setting via the `SetConsoleMode()` API function).  PuTTYcyg provides a POSIX pty in the Cygwin environment; it does not provide a Windows console device.

There are some excellent technical documents which explain why (non-Cygwin) Windows console programs don't work well in the absence of a Windows console device:

  * [Noncygwin programs wait for buffer to fill before outputting to ssh](http://www.cygwin.com/ml/cygwin/2003-12/msg00575.html)
  * [Capturing console I/O in Win32](http://homepages.tesco.net/~J.deBoynePollard/FGA/capture-console-win32.html)
  * [PuTTY wish win-command-prompt](http://www.chiark.greenend.org.uk/~sgtatham/putty/wishlist/win-command-prompt.html)

## Startup is really slow. ##
This could be due to [bash loading slowly](http://code.google.com/p/puttycyg/issues/detail?id=50).  Try launching PuTTYcyg with Command set to `bash --noprofile --norc`.  If this is faster, run PuTTYcyg with `bash -v` to see which parts of your bash setup are slow.

This could also be a problem with local firewall software.  PuTTYcyg uses a local TCP port to communicate between putty.exe and cthelper.exe.

## PuTTYcyg "doesn't work". ##
If you get a strange error message or if PuTTYcyg hangs as soon as you launch a Cygterm session (but works fine with SSH), the problem may be multiple copies of `cygwin1.dll`.  See [the Cygwin FAQ](http://cygwin.com/faq/faq-nochunks.html#faq.using.multiple-copies) and search your system for multiple copies of this file.

## Troubleshooting: "Invalid Port number" ##
If the session registry has an old configuration, PuTTYcyg may not start properly.  Changing the `PortNumber` setting in `HKEY_CURRENT_USER\SOFTWARE\SimonTatham\PuTTY\Sessions\_SESSION_` to `1` should solve the problem.

## Troubleshooting: "The procedure entry point blahblah could not be located in the dynamic link library cygwin1.dll" ##
This is a sure sign that your Cygwin installation predates 1.7.  Please upgrade to Cygwin 1.7 or use [the last PuTTYcyg version which supports Cygwin 1.5 (20071202)](http://puttycyg.googlecode.com/files/puttycyg-20071202.zip).

## Other questions ##
For questions specific to PuTTYcyg, please feel free to [create an issue](http://code.google.com/p/puttycyg/issues/entry).

Please consult the [Cygwin FAQ](http://cygwin.com/faq.html) or the [PuTTY FAQ](http://www.chiark.greenend.org.uk/~sgtatham/putty/faq.html) for questions not directly related to PuTTYcyg.

Comments here are nice, but will not receive replies in a timely manner.  Please [create an issue](http://code.google.com/p/puttycyg/issues/entry) to have your support question answered!