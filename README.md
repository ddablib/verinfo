# Version Information Component

## Contents

* [Description](#description)
* [Installation](#installation)
* [Demo Projects](#demo-projects)
* [Update History](#update-history)
* [License](#license)
* [Bugs and Feature Requests](#bugs-and-feature-requests)
* [About the Author](#about-the-author)

## Description

_TPJVersionInfo_ is a 32 bit non-visual component versions of Delphi (except .NET) that encapsulates the version information contained in an executable file's resources.

The component reads information from a designated file's VERSIONINFO resource. The required file is specified in the component's _FileName_ property. Setting _FileName_ to the empty string fetches version information for the executable file containing the component. The Boolean _HaveInfo_ property indicates whether the file contains version information. This component can access variable file information for each language provided in the resource.

Run-time properties enable access to to version information. Properties enable:

* Access to fixed file information, either by field or the whole record.
* Access to the number of translations stored in the version information.
* Selection of the translation for which information is to be returned by other properties.
* Access to the language and code page of the current translation – by code and by name.
* Access to the string file information for the current translation – named properties access the Microsoft-defined string information, while an array property gives access to any string item by name.

Version numbers are encapsulated in _TPJVersionNumber_ records which, on Delphi 2006 or later, can be directly assigned to a string and can be compared using the normal equality operators. Helper functions are also provided for use with earlier Delphis that can format version numbers as text and can compare them.

For more information read the [online documentation](https://delphidabbler.com/url/verinfo-docs).

### Limitations

The component makes calls to the Windows API. Therefore the version information being read must follow the Microsoft guidelines – be warned that not all software complies!

### Compatibility

_TPJVersionInfo_ compiles on all Win32 versions and personalities of Delphi. Releases up v3.3 have tested with Delphi versions 2, 3, 4, 6, 7, 2006 and 2010 while later releases have been tested on Delphi 7 and 2006 to XE4 and are assumed to work on later versions.

The unit name changed to `PJVersionInfo` at release 3 – this means that programs using earlier versions will need to be modified (or to have an alias set in Delphi's Project Options) before being recompiled using the new version. Functionally, the component is backward compatible with earlier versions.

### Further information

For detailed information about version information refer to the Windows SDK.

## Installation

> **Important Note:** If you are updating from an earlier version of this component and have installed the _DelphiDabbler_ [_About Box Component_](https://delphidabbler.com/software/aboutbox) (_TPJAboutBoxDlg_) you may need to uninstall it before updating this component, and re-install the about box component once the update has been installed. If the _About Box Component_ is earlier that v3.2 it will need to be updated to the most recent version.

The _Version Information Component_ is supplied in a zip file. Before installing you need to extract all the files from the zip file. The following files will be extracted:

* **`PJVersionInfo.pas`** – Component source code.
* **`PJVersionInfo.dcr`** – Component palette glyph.
* `README.md` – This read-me file.
* `CHANGELOG.md` – Change log.
* `MPL-2.txt` – Mozilla Public License v2.0.
* `Documentation.URL` – Short-cut to the component's online documentation.

In addition to the above files you will find the the source code of two [demo projects](#demo-projects) along with read-me files in the `Demos\1` and `Demos\2` sub-directories.

You can now install the component into the Delphi IDE.

For Delphi 3 onwards you must include `PJVersionInfo.pas` and `PJVersionInfo.dcr` in a design time package that is installed into the Delphi IDE. If you need help doing this [see here](https://delphidabbler.com/url/install-comp).

## Demo Projects

The source code for two demo projects is included. The demos are:

1. `VIDemo.dpr` is an application that can extract and display version information from any program (provided that the program has valid version information).
2. `HelpEgs.dpr` implements all the [examples](https://delphidabbler.com/url/verinfo-egs) from the online documentation and help file.

These demos require Delphi 7 or later.

> **Note:** To load the projects into Delphi 2007 first delete the relevant `.dproj` file and then load the project from the `.bdsproj` file.

With some minor changes the demos will also compile as 64 bit Windows targets using the 64 bit Delphi. (Tested with Delphi XE2, 3, and 4). To do this create a 64 bit Windows target, ensure that the compiler can find the component source file (or a 64 bit compiled unit) and disable automatic version information generation.

## Update History

A complete change log is provided in [`CHANGELOG.md`](https://github.com/ddablib/verinfo/blob/main/CHANGELOG.md) that is included in the download.

## License

This component is released under the terms of the [Mozilla Public License v2.0](https://www.mozilla.org/MPL/2.0/).

## Bugs and Feature Requests

Bugs can be reported or new features requested via the project's [Issue Tracker](https://github.com/ddablib/verinfo/issues). A GitHub account is required.

Please check if an issue has already been created for a similar report or request. If so then please add a comment containing as much information as you can to the existing issue, or if you've nothing to add, just add a :+1: (`:+1:`) comment. If there is no suitable existing issue then please add a new issue and give as much information as possible.

## About the Author

I'm Peter Johnson – a hobbyist programmer living in Ceredigion in West Wales, UK, writing mainly in Delphi. My programs and other library code are available from: [https://delphidabbler.com/](https://delphidabbler.com/).

This document is copyright © 2005-2022, [P D Johnson](https://gravatar.com/delphidabbler).
