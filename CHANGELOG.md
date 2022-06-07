# Change Log for Version Information Component

## v3.3.2 of 11 January 2014

+ Fixed problem with compiler directives in component and demo source files that was causing compilation to fail on Delphi XE5.
+ Fixed demo 1 to remove warning when compiled with Delphi XE3 and later.
+ Minor documentation tweaks and corrections.

## v3.3.1 of 14 January 2013

+ Unit names are now qualified with namespace name on Delphi XE2 and later.
+ Changes to demo projects:
  + Font and appearance of some controls changed.
  + Controls are now themed.
  + All form files now in text format.
  + Forms are no longer scaled.
  + 1st demo program's main window now resizes.
  + 2nd demo dialogues' "help" button now display online examples instead of help file topics.
  + Demos now need Delphi 7 as a minimum.
  + New project configurations files.
+ Component source license changed to Mozilla Public License v2.0. (Demos now placed in public domain).
+ MPL text file and documentation wiki short-cut have had names changed.
+ WinHelp help file regenerated with updated copyright date.
+ Documentation revised.

## v3.3 of 03 November 2010

+ Added operator overloads to _TPJVersionNumber_ record when compiled with Delphi 2006 and later to:
  + Support equality tests using `=`, `<>`, `<`, `<=`, `>` and `>=` operators.
  + Support implicit casting to a string which formats the version number as a dotted quad ~~(issue #12)~~.
+ Added new helper functions primarily for use with Delphi 2005 and earlier:
  + _CompareVerNums_ - compares two version number records.
  + _VerNumToStr_ - formats a version number as a dotted quad.
+ Updated _TPJVersionNumber_ topic in help file re changes.
+ Updated HTML documentation.

## v3.2 of 09 November 2009

+ Changed method used to get character set descriptions. These are now obtained from operating system where possible instead of from hard-wired values.
+ Added compiler directive to switch off unsafe code warnings on compilers that support the directive.
+ Added copy of Mozilla Public License v1.1.
+ Corrected error in help file.
+ Modified Demo 2 to enable it to compile on Delphi 2 and 3.
+ Updated documentation and included short-cut file that links to component Wiki.

## v3.1.1 of 11 December 2005

+ Changed component to Mozilla public license v1.1.
+ Fixed minor bug in _VIDemo_ project.
+ Revised _HelpEgs_ demo project to access related help file topics.
+ Updated help file to make examples available from component's main page.
+ Updated HTML documentation.

## v3.1 of 07 September 2003

+ Fixed to be compatible with C++ Builder - direct access to fields of _TVSFixedFileInfo_ in property declarations were replaced by calls to an indexed property getter function.

## v3.0.1 of 08 July 2003

+ Changed component palette from `PJSoft` to `DelphiDabbler`.
+ Updated HTML documentation.
+ Changed copyright message in help file.

## v3.0 of 17 February 2002

+ Added ability to access all "translations" stored in a file's version information, rather than just first one. This has been done so that code using earlier versions of this component should continue to work unchanged.
+ Added new property to expose fixed file information record.
+ Added new "string array" property to give access to string information by name: this property can access any custom string information if the name is known.
+ Added properties to return number of "translations" and to select index of "translation" to be used.
+ Added properties to return language and character set codes in addition to descriptive strings.
+ All string info, language and character set properties now return values from the currently selected translation (which defaults to the first translation maintaining backward compatibility).
+ Empty _FileName_ property now accesses name of host application per command line rather than using _Application.ExeName_.
+ CharSet property now returns `''` for unknown value rather than `'Unknown'`.
+ Renamed _TVersionNumber_ record to _TPJVersionNumber_.
+ Replaced _Tvs_FixedFileInfo_ record with use of Windows unit defined type _TVSFixedFileInfo_.
+ Renamed unit to _PJVersionInfo_.
+ Changed component palette from `PJ Stuff` to `PJSoft`.
+ Added two demo programs, one is a sample version information reading program and the other implements examples from the help file.

## v2.1 of 28 November 1999

+ Changed unit name from _VerInfo_ to _VInfo_ to allow component to install under Delphi 3 & 4 (_VerInfo_ clashes with an existing unit in these versions).
+ Removed superfluous conditional compilation directives.
+ Updated HTML documentation to separate 16 bit from 32 bit version, to to include installation notes for Delphi 3/4 and to include update history.

## v2.0.1 of 08 July 1999

+ Changed palette where component installs to `PJ Stuff` from `Own`.
+ Added HTML documentation (shared documentation with Release 1.0.1).
+ Included 16 bit Version Information Component release v1.0.1

## v2.0 of 06 December 1998 {Never publicly released}

+ Forked development - 32 bit development (this fork) began with v2.0 while the 16 bit version continued with v1.0.1
+ Revised for use with Win32 - not backwards compatible with v1.0

## v1.0 of 26 April 1998 {Never publicly released}

+ Original version - 16 bit only.
