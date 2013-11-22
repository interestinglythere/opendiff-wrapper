opendiff-wrapper
================

There are a few problems with `opendiff`, Apple's command-line interface to the GUI diff tool FileMerge:

- It won't launch FileMerge if Xcode is on a non-startup volume ("launch path not accessible").
- It takes too long to recognize when the user has closed a diff window.
- It prepends error lines with an ugly log-like header: `2013-11-22 02:54:44.734 opendiff[90964:1007]` or something of the like.

This wrapper script solves all these problems with minimal overhead. Put this in your `PATH` but obviously not in `/usr/bin/opendiff`.

Use `opendiff --nowait [args-to-opendiff]` to remove the delay between closing a FileMerge window and the next command prompt by running the underlying `opendiff` asynchronously as a background job.
