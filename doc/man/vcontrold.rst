===========
 vcontrold
===========

----------------------------------------------------------
Unix daemon for communication with Viessmann Vito heatings
----------------------------------------------------------

:Author: Frank Nobis fn@radio-do.de,
         other contributors see `vcontrold @GitHub <https://github.com/openv/vcontrold>`__
:Copyright: GPLv3
:Manual section: 1

SYNOPSIS
========

  vcontrold [-x <xml-file>] [-d <device>] [-l <logfile>] [-p <port>] [-s] [-n] [-g] [-v] [-V]

DESCRIPTION
===========

vcontrold uses a serial optical link or an IP connection to communicate with
a Viessmann vito heating controller.

OPTIONS
=======

-x <xml-file>, \--xmlfile <xml-file>
    location of the main config file

-d <serial-device>, \--device <serial-device>
    serial device to use.
    This option overrides corresponding entry in the config file.

-p <port>, \--port <port>
    TCP <port> to use for remote connections.
    The default is 3002 and can be specified
    in the config file.
    This option overrides the corresponding entry in the config file.

-s, \--syslog
    use syslog

-l <logfile>, \--logfile <logfile>
    use <logfile> instead of syslog.

-n, \--nodaemon
    do not fork. This is for testing purpose only. Normaly vcontrold
    will detach from the controlling terminal and put itself into the
    background.

-i, \--vsim
    use a temp file in ``/tmp/sim-devid.ini`` for use with the vsim simulator
    (developer option)

-c <command-file>, \--commandfile <command-file>
    file with lines containing sequences of icmds (WAIT, SEND, RECV, PAUSE)
    as used in protocol definitions.
    Lines get executed in order
    (developer option)

-g, \--debug
    enable debug mode

-v, \--verbose
    verbose mode

-V, \--Version
    print version information, then exit

\--help
    usage information

FILES
=====

``/etc/vcontrold/vcontrold.xml``
    These are the programm specific configurations. E.g. device, baudrate,
    IP etc.

``/etc/vcontrold/vito.xml``
    These are the command definitions for the devices in use.

LICENSE
=======

The vcontrold software, its accompanying files and documentation
are licensed under the **GPLv3**.
See COPYING in the package.

SEE ALSO
========

* man 1 vclient
* vcontrold @GitHub: `https://github.com/openv/vcontrold <https://github.com/openv/vcontrold>`__
