---
title: "Creating e-books with Eclipse"
layout: page 
pager: true
author: heeckhau (Sigasi)
date: 2012-02-08
tags: 
  - documentation
  - planeteclipse
---
<div class="content">
<p><span class="inline inline-right"><a href="http://www.sigasi.com/sites/www.sigasi.com/files/Sigasi-2.1.1.epub"><img src="http://www.sigasi.com/sites/www.sigasi.com/files/images/epub.png" alt="" title="" class="image image-_original " width="229" height="243"/></a></span>In November last year, I attended a very interesting session of <a href="http://eclipsecon.org/sessions/build-your-epubs-eclipse-and-read-them-too" class="elf-external elf-icon">Torkild Resheim about creating e-books in Eclipse</a> at EclipseCon Europe in Nuremburg. Torkild demonstrated a <a href="https://bugs.eclipse.org/bugs/show_bug.cgi?id=332122" class="elf-external elf-icon">new plugin</a>  he developed that converts wiki markup files into e-books. I intended to try this as soon as I got home from the conference. But I did not get to it until now.</p>	<p>The e-book plugin is a new extension to the wikitext component of the <a href="http://www.eclipse.org/projects/project.php?id=mylyn.docs" class="elf-external elf-icon">Mylyn Docs project</a>. It is not officially released yet, but here are some easy steps on how to create an e-book with Eclipse today:</p>	<ol><li>Clone the git repository of Torkild from github:     <span class="geshifilter"><code class="vhdl geshifilter-vhdl">git clone https<span style="color: #000066;">:</span>//github.com/turesheim/org.eclipse.mylyn.docs.git</code></span></li>		<li>Use Maven Tycho to build the Eclipse plugin:     <span class="geshifilter"><code class="vhdl geshifilter-vhdl">mvn install</code></span></li>		<li>Open Eclipse (I used <a href="http://www.eclipse.org/downloads/packages/eclipse-rcp-and-rap-developers/indigosr1" class="elf-external elf-icon">Eclipse for <span class="caps">RCP</span> developers</a>), and install the compiled plugins from <code>&lt;clonedRepoLocation&gt;/org.eclipse.mylyn.docs/org.eclipse.mylyn.docs-site/target/site</code></li>		<li>Open an existing project that contains your wikitext (in my case Textile) file</li>		<li>Make sure that your file contains no errors. The error messages you otherwise get in the next step are not so useful yet.</li>		<li>Right click the wikitext file and select <strong>WikiText &gt; Generate <span class="caps">EPUB</span>&#8230;</strong></li>		<li>Enter all extra metadata and optionally choose a stylesheet and cover image.</li>		<li>Open the epub file in an e-book reader and inspect the result. I used the open source tool <a href="https://launchpad.net/calibre" class="elf-external elf-icon">Calibre</a> for this.</li>	</ol><br/><p>As an experiment I created an <a href="http://www.sigasi.com/sites/www.sigasi.com/files/Sigasi-2.1.1.epub">e-book of the Sigasi 2.1.1 documentation</a>. I am really pleased by the result. It is great to read documents on a tablet and I hope this can be a good motivator to write some extra documentation.</p>	<p>Hendrik</p><table id="attachments" class="sticky-enabled"> <thead><tr><th>Attachment</th><th>Size</th> </tr></thead><tbody> <tr class="odd"><td><a href="http://www.sigasi.com/sites/www.sigasi.com/files/Sigasi-2.1.1.epub">Sigasi-2.1.1.epub</a></td><td>585.14 KB</td> </tr></tbody></table>  </div>
