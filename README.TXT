
wiringPi README
===============

Please note that the official way to get wiringPi is via git from
git.drogon.net and not GitHub.

ie.

  git clone git://git.drogon.net/wiringPi

The version of wiringPi held on GitHub by "Gadgetoid" is used to build the
wiringPython, Ruby, Perl, etc. wrappers for these other languages. This
version may lag the official Drogon release.  Pull requests may not be
accepted to Github....

Please see

  http://wiringpi.com/

for the official documentation, etc. and the best way to submit bug reports, etc.
is by sending an email to projects@drogon.net

Thanks!

  -Gordon

For CMake build system bugs and stuff, pull requests and bug reports are welcome.

Also board detection bugs (as this should be compatible with all OS, not just raspbian) welcome to me. We are using /sys rather than /proc. This allows to use 64bit ARM kernel.

  -Arto
