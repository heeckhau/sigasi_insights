---
title: "Missing libraries"
layout: page 
pager: true
author: heeckhau (Sigasi)
date: 2011-11-30
tags: 
  - hdt-2.0
---
<div class="content">
<p>When you import a new project in Sigasi, you often get a lot of problem markers because of missing <span class="caps">VHDL</span> libraries. By default all project files are mapped to <a href="http://www.sigasi.com/content/work-not-vhdl-library">library <strong>work</strong></a>. <span class="caps">VHDL</span> libraries are defined outside of your <span class="caps">VHDL</span> files. So Sigasi can not configure your libraries automatically. We have some good ideas for heuristics to guess the correct library mapping. But for now, you have to configure the library mapping yourself.</p>	<p><span class="inline inline-center"><img src="http://www.sigasi.com/sites/www.sigasi.com/files/images/1_gaislerWorkProblems.png" alt="Auch, 75753 errors in GRlib" title="Auch, 75753 errors in GRlib" class="image image-_original " width="408" height="431"/><span class="caption"><strong>Auch, 75753 errors in GRlib</strong></span></span></p>	<p>But if you have many thousands of problem markers because of missing libraries. <em>How do you easily find out which libraries are missing?</em> The easiest way is to filter the "Problems View":</p>	<ol><li>Click the menu icon in the problems view and select <strong>Configure Contents</strong> <span class="inline inline-center"><img src="http://www.sigasi.com/sites/www.sigasi.com/files/images/2_problemsMenu.png" alt="Problems View menu" title="Problems View menu" class="image image-_original " width="221" height="186"/><span class="caption"><strong>Problems View menu</strong></span></span></li>		<li>In the Configure Contents dialog:	<ol><li><em>Uncheck</em> "Show all items"</li>		<li>Add a <strong>New</strong> Configuration and <strong>Rename</strong> it to "Missing Libraries"</li>		<li>(Optionally) Click "On any element in same project" if you only want to see problems of the currently selected project.</li>		<li>In the text field of the Description type "Library"</li>		<li>Click OK <br/><span class="inline inline-center"><a href="http://www.sigasi.com/sites/www.sigasi.com/files/images/3_ConfigureProblemContents.png" onclick="launch_popup(1340, 870, 753); return false;" target="_blank"><img src="http://www.sigasi.com/sites/www.sigasi.com/files/images/3_ConfigureProblemContents.preview.png" alt="Configure Problem View Contents" title="Configure Problem View Contents" class="image image-preview " width="640" height="554"/></a><span class="caption"><strong>Configure Problem View Contents</strong></span></span></li>	</ol></li>	</ol><p>You will see a lot of duplicates, but once you start <a href="http://www.sigasi.com/documentation/2.1.1/sigasi.html#Modifyingthelibraryconfiguration">mapping the libraries correctly</a>, this number will quickly decrease.</p>	<p><span class="inline inline-center"><img src="http://www.sigasi.com/sites/www.sigasi.com/files/images/4_MissingLibraries.png" alt="Missing library markers" title="Missing library markers" class="image image-_original " width="490" height="177"/><span class="caption"><strong>Missing library markers</strong></span></span></p>	<p>Hendrik.</p>  </div>
