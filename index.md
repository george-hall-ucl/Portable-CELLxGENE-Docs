---
title: Home
layout: home
nav_order: 1
---

<center><img src="assets/images/favicon_new_export_small.svg"></center>

<center><h1>Portable-CELLxGENE</h1></center>

**Portable-CELLxGENE** is a standalone version of
[CELLxGENE](https://github.com/chanzuckerberg/cellxgene) and
[CELLxGENE-gateway](https://github.com/Novartis/cellxgene-gateway) to allow
single-cell transcriptomic data to be annotated without needing the command
line or extra software.

<br>
<center>
<h2>Click to install</h2>
<a href="https://github.com/george-hall-ucl/portable-cellxgene/releases/latest/download/Install-Portable-CELLxGENE.zip"><img src="assets/images/pcxg_docs_os_macos.png" alt="Download button for MacOS version." width="200"></a>
&nbsp;
<a href="https://github.com/george-hall-ucl/portable-cellxgene/releases/download/v1.4/Install-Portable-CELLxGENE-Windows_v1_4.exe"><img src="assets/images/pcxg_docs_os_windows.png" alt="Download button for Windows version." width="200"></a>
</center>
Having problems? Visit the [installation](installation.html) page.
<br>

## Running Portable-CELLxGENE

<details>
<summary>Click to reveal video of basic Portable-CELLxGENE usage</summary>
Recorded in MacOS, but the process is similar in Windows.
<kbd><img src="assets/images/PCxG_MacOS_demo.gif" alt="Gif showing basic Portable-CELLxGENE usage."></kbd>
</details>

1. A file browser will open. Navigate to the folder containing your `.h5ad` and
   click "Open".
2. A page listing the datasets should open in your browser. If it does not open
   after a minute, then navigate to
   [http://127.0.0.1:5005/portable_home.html](http://127.0.0.1:5005/portable_home.html)
   yourself. If the page opened automatically but is not displaying anything,
   then you may need to refresh it.
3. Follow the instructions on the homepage.
4. Once you are finished, close the CELLxGENE browser tab(s) and quit the
   app.

Note: Each annotation session will continue running in the background until
either the Portable-CELLxGENE app is terminated or the session is closed from
the "View running sessions" page (see end of above video). For large datasets,
this may slow down your computer so it is advisable to terminate them once you
are finished.

## How to use CELLxGENE

There are many guides on how to use CELLxGENE available online, for example a
basic introduction can be found
[here](https://icbi-lab.github.io/cellxgene-user-guide/). The official
documentation of CELLxGENE is
[here](https://cellxgene.cziscience.com/docs/01__CellxGene), which gives
in-depth information on its use.

