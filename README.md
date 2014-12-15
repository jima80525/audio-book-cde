audio-book-cde
==============

A simple wrapper around abcde to rip multi-disc audiobooks

This script came out of a personal need and, at this point, is designed entirely
around what my workflow looks like.  It was not originally designed to be a
general purpose tool and might not fit your needs perfectly.  If not, please
fork and let me know.  I'm happy to spend some more time on it.

Here's my use case for the tool.  I frequently get audiobooks on CD which I want
to rip to MP3 files.  I want an automated system for ripping those discs, ending
with a directory structure that looks like:

      author
      ├── title-Disc-1
      │   ├── 1.Track_1.mp3
      │   ├── 2.Track_2.mp3
      │   └── 3.Track_3.mp3
      ├── title-Disc-2
      │   ├── 1.Track_1.mp3
      │   ├── 2.Track_2.mp3
      │   └── 3.Track_3.mp3
      └── title-Disc-3
          └── 1.Track_1.mp3
      [etc]

Abcde does quite a lot of this, but getting the multi-disc aspect of it seemed
outside the scope of that product.  This script is just a bash shell wrapper
around abcde to generate that format.

Installation
============
Simply copy the script to a location in your PATH and type

   audio-book-cde <author> <book-title> <number-of-discs> [abcde conf file]

If you do not specify a conf file for abcde, one will be provided for you.  The
contents of this conf file are visible in the script itself, but they basically
tell abcde to not prompt, to not query cddb and to put the files in the desired
directory structure.

*Note* You must have abcde installed with all of the other applications needed
to rip into your desired format.

Compatibility issues
=====================
Note that I wrote and tested this script on linux-mint 17 (Qiana).  I make no
promises that this will work on other versions of linux.

The most likely issue you will run into will be with the wait_for_cd function
which seems like it might not be universal.

The rest of it is fairly vanilla bash.
