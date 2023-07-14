=============
paperwork-gtk
=============

----------------------------------
Manages scanned documents and PDFs
----------------------------------

:Author: Thomas Perret, 2019-2020
:Version: 2.0
:Copyright: GPL-3.0+
:Manual section: 1
:Manual group: User commands

SYNOPSIS
========
paperwork-gtk [-h] command

DESCRIPTION
===========
Paperwork is a personal document manager.

It manages scanned documents and PDFs. It's designed to be easy and fast to use.
The idea behind Paperwork is "scan & forget": You can just scan a new document
and forget about it until the day you need it again. In other words, let the
machine do most of the work for you.

OPTIONS
=======
-h, --help    show this help message and exit

**plugins** `subcommand`
 Manage paperwork-gtk plugins

  `list`
   Show plugins enabled for paperwork-gtk
  `add`
   Add plugin in paperwork-gtk
  `remove`
   Remove plugin from paperwork-gtk
  `reset`
   Clean up your mess by resetting the plugin list to its default value
  `show`
   Show information regarding a plugin (must be enabled)

**config** `subcommand`
 Manage Paperwork configuration

  `get`
   Get a value from Paperwork's configuration
  `put`
   Set a value in Paperwork's configuration
  `show`
   Show Paperwork's configuration
  `list_types`
   Show value types you can use from command line

SEE ALSO
========
* paperwork-cli(1), paperwork-json(1)
* The paperwork frontend introduction (file:///usr/share/doc/paperwork-gtk/intro.pdf)
* The paperwork frontend usage manual (file:///usr/share/doc/paperwork-gtk/usage.pdf)
