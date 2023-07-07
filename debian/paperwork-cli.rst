=============
paperwork-cli
=============

--------------------------
cli interface to paperwork
--------------------------

:Author: Thomas Perret, 2019-2020
:Version: 2.0
:Copyright: GPL-3.0+
:Manual section: 1
:Manual group: User commands

SYNOPSIS
========
paperwork-cli [-h] command

DESCRIPTION
===========

Interactive shell frontend for Paperwork.

OPTIONS
=======
-h, --help    Show help for paperwork-shell

**sync**
 Synchronize the index(es) with the content of the work directory

**show** [`--pages`]
 Show the content of a document

  `--pages`
   Pages to show: 1,4 or 1-10 (default: all)

**search** [`--limit`]
 Search keywords in documents

  `--limit, -l` *LIMIT*
   Maximum number of results (default: 50)

**scanner** `subcommand`
 Manage scanner configuration

  `list`
   List all scanners and their possible settings

  `get`
   Show the currently selected scanner and its settings

  `set` [`--source` SOURCE] [`--resolution` RESOLUTION] `device_id`
   Define which scanner and which settings to use

   `--source` SOURCE
    Default source on the scanner to use (if not specified, one will be selected randomly)

   `--resolution` RESOLUTION, `-r` RESOLUTION
    Default resolution (dpi ; default=300)

**scan** [`--doc_id` DOC_ID] `source_id``
 Scan pages

 `--doc_id` DOC_ID, `-d` DOC_ID
  Document to which the scanned pages must be added

**reset** [`--pages` PAGES] doc_id
 Reset a page to its original content

 `--pages` PAGES, `-p` PAGES

**rename** `source_doc_id` `dest_doc_id`
 Change a document identifier

 `source_doc_id`
  Document to rename

 `dest_doc_id`
  New name for the document

**ocr** [`--pages` PAGES] doc_id
 OCR document or pages

 `--pages` PAGES, `-p` PAGES
  Pages to OCR  (single integer, range or comma-separated list, default: all pages)

**move** `source_doc_id` `source_page` `dest_doc_id` `dest_page`
 Move a page

 `source_doc_id`
  Source document

 `source_page`
  Page to move

 `dest_doc_id`
  Destination document

 `dest_page`
  Target page number

**label** `subcommand`
 Commands to manage labels

 `list`
  Show labels
  
 `show` [`doc_ids` [`doc_ids` ...]]
  Show labels from doc_ids
  
  `doc_ids`
   Document(s) 
  
 `add` [`--color` COLOR] `doc_id` `label_name`
  Add label `label_name` to document `doc_id` with optional color `COLOR`

 `remove` `doc_id` `label_name`
  Remove label `label_name` from document `doc_id`

 `delete` `label_name`
  Delete label `label_name`

**import** [`--doc_id` DOC_ID] [`files` [`files` ...]]
 Import file(s)

 `files`
  Files to import

 `--doc_id`, `--doc`, `-d` DOC_ID
  Target document for import

**extra_text** `subcommand`
 Manage additional text attached to documents

 `get`
  Get a document additional text

 `set`
  Set a document additional text

**export** [`--pages` PAGES] [`--filters` FILTERS] [`--out` OUT] `doc_id`
 Export a document, a page, or a set of pages.

 `doc_id`
  Document to export

 `--pages`, `-p` PAGES
  Pages to export (single integer, range or comma-separated list, default: all pages)

 `--filters`, `-f` FILTERS
  Export filters. Specify this option once for each filter to apply (ex: '-f grayscale -f jpeg').

 `--out`, `-o` OUT
  Output file/directory. If not specified, will list the filters that could be chained after those already specified.

**edit** [`--modifiers` MODIFIERS] [`--pages` PAGES] doc_id
 Edit page

 `doc_id`

 `--modifiers`, `-m` MODIFIERS
  List of image modifiers (comma separated, possible values: ['rotate_clockwise', 'rotate_counterclockwise', 'color_equalization'])
  
 `--pages`, `-p` PAGES

**delete** [`--pages` PAGES] [`doc_ids` [`doc_ids` ...]]
 Delete a document or a page

 `doc_ids`
  Target documents

 `--pages`, `-p` PAGES
  Pages to delete (single integer, range or comma-separated list, default: all pages)

**about**
 About Paperwork

**plugins** `subcommand`
 Manage paperwork-cli plugins

 `list`
  Show plugins enabled for paperwork-cli

 `add`
  Add plugin in papaerwork-cli

 `remove`
  Remove plugin from paperwork-cli

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

EXAMPLE
=======
* Export a document:

  `paperwork-cli` export 20150303_2314_39 -p 2 -f img_boxes -f grayscale -f jpeg -o ~/tmp/pouet.jpg

SEE ALSO
========
* paperwork-json(1), paperwork-gtk(1)
* The paperwork frontend introduction (file:///usr/share/doc/paperwork-gtk/intro.pdf)
* The paperwork frontend usage manual (file:///usr/share/doc/paperwork-gtk/usage.pdf)
