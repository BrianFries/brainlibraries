# BrainScan Libraries for WebDNA

[WebDNA](http://www.webdna.us) is a long-lived yet relatively obscure web server scripting environment for Linux- and macOS-based web servers

The BrainScan Libraries contain a great many utility functions to extend the usefulness and ease of developing complex WebDNA sites.

## Requirements
- WebDNA version 6.2 or later, tested through WebDNA version 8.5

## The Libraries
- *brainutility.lib* contains general purpose functions. My WebDNA sites include this on every page.
- *brainform.lib* (Coming Soon!) contains functions useful for presenting, validating and processing web page forms.
- *brainepoch.lib* (Coming Soon!) contains functions for working with timestamps, converting between WebDNA's numeric date (days since the year zero) and time (seconds since midnight) values and timestamps based either from year zero or the Unix standard year 1970.
- *brainobject.lib* (Coming Soon!) contains advanced functions that add an object-oriented way of working with WebDNA variables and functions.

See the reference documentation for each library inside the *documentation* folder

## Installation
These library files may be placed anywhere on your server that is accessible to WebDNA pages when they are interpreted. Standard locations are:
- WebDNA Fast-CGI versions: /brainscan/library/\*, within the file hierarchy for each site they are to be used by
- WebDNA Server versions: ^/brainscan/library/\*, in the globals area where all sites on the server may access the same copies of the library files
