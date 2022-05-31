<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<!--
 * This Source Code Form is subject to the terms of the Mozilla Public License,
 * v. 2.0. If a copy of the MPL was not distributed with this file, You can
 * obtain one at http://mozilla.org/MPL/2.0/
 *
 * Copyright (C) 2005-2014, Peter Johnson (www.delphidabbler.com).
 *
 * Read-me file for Version Information Component.
-->
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en">

<head>

<title>
  DelphiDabbler Version Information Component ReadMe
</title>

<style type="text/css">
  body {
    margin: 1em;
    padding: 0;
    font-family: Verdana, Arial, sans-serif;
    font-size: 9pt;
    line-height: 150%;
  }
  h1 {
    margin: 0 0 1em 0;
    padding: 0.5em;
    border: 1px silver solid;
    background-color: #eee;
    font-size: 13pt;
    font-weight: bold;
    text-align: center;
  }
  h1 .subtitle {
    font-style: italic;
    color: #336;
  }
  h2 {
    margin: 1em 0 0 0;
    padding: 0;
    padding-bottom: 6px;
    border-bottom: 1px silver solid;
    font-size: 11pt;
    font-weight: bold;
  }
  h3 {
    margin: 0.5em 0 0 0;
    padding: 0;
    font-size: 9pt;
    font-weight: bold;
  }
  p {
    margin: 0.5em 0 0 0;
    padding: 0;
  }
  ul, ol {
    margin: 0.5em 0 0 3em;
    padding: 0;
  }
  ul {
    list-style-type: square;
  }
  ul.spaced li,
  ol.spaced li {
    margin-top: 0.5em;
  }
  ul.spaced li,
  ol.spaced li {
    margin-top: 0.5em;
  }
  ul.unspaced li,
  ol.unspaced li {
    margin-top: 0;
  }
  ul.unspaced li.first,
  ol.unspaced li.first {
    margin-top: 0.5em;
  }
  code {
    font-family: "Courier New", Courier, monospace;
  }
  a:link {
    color: #336;
    text-decoration: underline;
  }
  a:visited {
    color: #669;
    text-decoration: underline;
  }
  a:active {
    color: #336;
    text-decoration: underline;
  }
  a:hover {
    text-decoration: underline;
  }
  .pullout {
    border-left: 8px silver solid;
    background-color: #eee;
    margin: 0.5em 0 0 0;
    padding: 0.25em 0.5em;
    font-style: italic;
  }
  .indent {
    margin-left: 3em;
  }
  .highlight {
    color: #336;
    font-style: italic;
    font-weight: bold;
  }
  .endnotes {
    margin: 1.5em 0 0 0;
    padding: 1em 0 0 0;
    border-top: 1px silver solid;
  }
  .comments {
    font-style: italic;
  }
  .copyright,
  .copyright a:link,
  .copyright a:visited,
  .copyright a:active {
    margin: 1em 0 0 0;
    color: gray;
    font-size: 8pt;
    text-align: right;
  }
  </style>

</head>

<body>

<h1>
  <div>Version Information Component</div>
  <div class="subtitle">ReadMe</div>
</h1>

<h2 id="contents">
  Contents
</h2>

<ul>
  <li><a href="#description">Description</a></li>
  <li><a href="#installation">Installation</a></li>
  <li><a href="#demo">Demo Projects</a></li>
  <li><a href="#update">Update History</a></li>
  <li><a href="#license">License</a></li>
  <li><a href="#bugs">Bugs and Feature Requests</a></li>
  <li><a href="#author">About the Author</a></li>
</ul>

<h2 id="description">
  Description
</h2>

<p>
  <var>TPJVersionInfo</var> is a 32 bit non-visual component for all Win32
  versions of Delphi that encapsulates the version information contained in an
  executable file's resources.
</p>

<p>
  The component reads information from a designated file's
  <var>VERSIONINFO</var> resource. The required file is specified in the
  component's <var>FileName</var> property. Setting <var>FileName</var> to the
  empty string fetches version information for the executable file containing
  the component. The boolean <var>HaveInfo</var> property indicates whether the
  file contains version information. This component can access variable file
  information for each language provided in the resource.
</p>

<p>
  Run-time properties enable access to to version information. Properties
  enable:
</p>

<ul>
  <li>
    Access to fixed file information, either by field or the whole record.
  </li>
  <li>
    Access to the number of translations stored in the version information.
  </li>
  <li>
    Selection of the translation for which information is to be returned by
    other properties.
  </li>
  <li>
    Access to the language and code page of the current translation &ndash; by
    code and by name.
  </li>
  <li>
    Access to the string file information for the current translation &ndash;
    named properties access the Microsoft-defined string information, while an
    array property gives access to any string item by name.
  </li>
</ul>

<p>
  Version numbers are encapsulated in <var>TPJVersionNumber</var> records which,
  on Delphi 2006 or later, can be directly assigned to a string and can be
  compared using the normal equality operators. Helper functions are also
  provided for use with earlier Delphis that can format version numbers as text
  and can compare them.
</p>

<h3>
  Limitations
</h3>

<p>
  The component makes calls to the Windows API. Therefore the version
  information being read must follow the Microsoft guidelines &ndash; be warned
  that not all software complies!
</p>

<h3>
  Compatibility
</h3>

<p>
  <var>TPJVersionInfo</var> compiles on all Win32 versions and personalities of
  Delphi. Releases up v3.3 have  tested with Delphi versions 2, 3, 4, 6, 7, 2006
  and 2010 while later releases have been tested on Delphi 7 and 2006 to XE4 and
  are assumed to work on later versions.
</p>

<p>
  The unit name changed to <code>PJVersionInfo</code> at release 3 &ndash; this
  means that programs using earlier versions will need to be modified (or to
  have an alias set in Delphi's Project Options) before being recompiled using
  the new version. Functionally, the component is backward compatible with
  earlier versions.
</p>

<h3>
  Further information
</h3>

<p>
  For detailed information about version information refer to the Windows SDK.
</p>

<h2 id="installation">
  Installation
</h2>

<div class="pullout">
  <strong>Important Note:</strong> If you are updating from an earlier version
  of this component and have installed the <em>DelphiDabbler</em> About Box
  Component (<var>TPJAboutBoxDlg</var>) you may need to uninstall it before
  updating this component, and re-install the about box component once the
  update has been installed. If the About Box Component is earlier that v3.2 it
  will need to be updated to the most recent version.
</div>

<p>
  The <em>Version Information Component</em> is supplied in a zip file. Before
  installing you need to extract all the files from the zip file. The following
  files will be extracted:
</p>

<ul>
  <li>
    <strong><code>PJVersionInfo.pas</code></strong> &ndash; Component source
    code.
  </li>
  <li>
    <strong><code>PJVersionInfo.dcr</code></strong> &ndash; Component palette
    glyph.
  </li>
  <li>
    <code>PJVersionInfo.hlp</code> &ndash; Help file that integrates into the
    Delphi 3-7 IDE.
  </li>
  <li>
    <code>PJVersionInfo.als</code> &ndash; Keyword file required when
    integrating the help file with Delphi 6 and 7.
  </li>
  <li>
    <code>ReadMe.htm</code> &ndash; This read-me file.
  </li>
  <li>
    <code>ChangeLog.txt</code> &ndash; Change log.
  </li>
  <li>
    <code>MPL-2.txt</code> &ndash; Mozilla Public License v2.0.
  </li>
  <li>
    <code>Documentation.URL</code> &ndash; Short-cut to the component's online
    documentation.
  </li>
</ul>

<p>
  In addition to the above files you will find the the source code of two <a
    href="#demo"
  >demo projects</a> along with read-me files in the <code>Demos\1</code> and
  <code>Demos\2</code> sub-directories.
</p>

<p>
  You can now install the component into the Delphi IDE.
</p>

<p>
  For Delphi 3 onwards you must include <code>PJVersionInfo.pas</code> and
  <code>PJVersionInfo.dcr</code> in a design time package that is installed into
  the Delphi IDE. If you need help doing this <a
    href="http://www.delphidabbler.com/url/install-comp"
  >see here</a>.
</p>

<p>
  Note that the help file included in the download can only integrate with the
  IDE in Delphi 3-7. For information on how to do this, see <a
    href="http://www.delphidabbler.com/articles?article=15"
  >this article</a>. Users of other versions of Delphi can either use the help
  file as a stand-alone file (in which case some links won't work) or you can
  use the component's <a
    href="http://www.delphidabbler.com/url/verinfo-docs"
  >online documentation</a>.
</p>

<h2 id="demo">
  Demo Projects
</h2>

<p>
  The source code for two demo projects is included. The demos are:
</p>

<ol class="spaced">
  <li>
    <code>VIDemo.dpr</code> is an application that can extract and display
    version information from any program (provided that the program has valid
    version information).
  </li>
  <li>
    <code>HelpEgs.dpr</code> implements all the <a
      href="http://delphidabbler.com/url/verinfo-egs"
    >examples</a> from the online documentation and help file.
  </li>
</ol>

<p>
  These demos require Delphi 7 or later.
</p>

<p>
  <strong>Note:</strong> To load the projects into Delphi 2007 first delete the
  relevant <code>.dproj</code> file and then load the project from the
  <code>.bdsproj</code> file.
</p>

<div class="pullout">
  With some minor changes they will also compile as 64 bit Windows targets using
  the 64 bit Delphi. (Tested with Delphi XE2, 3, and 4). To do this create a 64
  bit Windows target, ensure that the compiler can find the component source
  file (or a 64 bit compiled unit) and disable automatic version information
  generation.
</div>

<h2 id="update">
  Update History
</h2>

<p>
  A complete change log is provided in a text file that is included in the
  download.
</p>

<h2 id="license">
  License
</h2>

<p>
  This component is released under the terms of the <a
    href="http://www.mozilla.org/MPL/2.0/"
  >Mozilla Public License v2.0</a>.
</p>

<h2 id="bugs">
  Bugs and Feature Requests
</h2>

<p>
  Bugs can be reported or new features requested via the <a
    href="http://www.delphidabbler.com/url/ddlib-issues"
  >Issue Tracker</a>.
</p>

<p>
  If no similar report or request has been recorded already, use the <em>New
  Issue</em> link to add a new issue. Please select the <em>Defect Report from
  User</em> template and be sure to specify the <code>Project-verinfo</code>
  label.
</p>

<p>
  Feature requests are also made using the Issue Tracker. This time please
  select the <em>Feature Request</em> template and, again, specify the
  <code>Project-verinfo</code> label.
</p>

<h2 id="author">
  About the Author
</h2>

<p>
  I'm Peter Johnson &ndash; a hobbyist programmer living in Ceredigion in West
  Wales, UK, writing write mainly in Delphi. My programs and code are available
  from: <a
    href="http://www.delphidabbler.com/"
  >http://www.delphidabbler.com/</a>.
</p>

<p>
  I can be <a
    href="http://www.delphidabbler.com/contact"
  >contacted via the website</a>.
</p>

<div class="endnotes">

  <div class="comments">
    Please <a
      href="http://www.delphidabbler.com/contact"
    >let me know</a> if you have any comments about the component, but please
    use the Issue Tracker noted above to report bugs and request new features.
  </div>

  <div class="copyright">
    This document is copyright &copy; 2005-2014, P D Johnson, <a
      href="http://www.delphidabbler.com/"
    >www.delphidabbler.com</a>.
  </div>

</div>

</body>

</html>
