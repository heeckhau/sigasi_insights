---
title: "Build Eclipse documentation from wikitext with Maven Tycho"
layout: page 
pager: true
author: heeckhau (Sigasi)
date: 2011-08-16
tags: 
  - eclipse
  - maven
  - planeteclipse
  - tycho
---
<div class="content">
<p>For <a href="http://www.sigasi.com/sigasi-20">Sigasi 2.0</a> we decided to write all documentation in the <a href="http://en.wikipedia.org/wiki/Textile_(markup_language)" class="elf-external elf-icon">textile</a> wiki markup language. With the <a href="http://wiki.eclipse.org/Mylyn/FAQ#WikiText" class="elf-external elf-icon">Mylyn Wikitext</a> plugin, textile files can be converted in lots of different output formats such as Eclipse help, html, pdf,&#8230;</p>	<p>Based on the <a href="http://www.peterfriese.de/advanced-wikitext/" class="elf-external elf-icon">blog posts of Peter Friese</a> I could easily automate the documentation build with Ant. But when I tried to run the documentation build ant task from our Maven Tycho build, the necessary <span class="caps">XSLT</span> transforms refused to run. <a href="http://xml.apache.org/xalan-j" class="elf-external elf-icon">Xalan</a> could not be loaded&#8230;</p>	<p>After a lot of googling, moaning and trying I finally found out that the trick is to add Xalan as a dependency to the antrun plugin.</p>	<p>This is the Maven configuration I ended up with that works for me: </p><pre><code>  &lt;build&gt;    &lt;plugins&gt;      &lt;plugin&gt;        &lt;groupId&gt;org.apache.maven.plugins&lt;/groupId&gt;        &lt;artifactId&gt;maven-antrun-plugin&lt;/artifactId&gt;        &lt;version&gt;1.6&lt;/version&gt;        &lt;executions&gt;          &lt;execution&gt;            &lt;id&gt;generate-documentation&lt;/id&gt;            &lt;phase&gt;generate-sources&lt;/phase&gt;            &lt;configuration&gt;              &lt;echo&gt;Generating documentation&lt;/echo&gt;              &lt;tasks&gt;                &lt;property name="compile_classpath" refid="maven.compile.classpath" /&gt;                &lt;ant inheritRefs="true" antfile="build-doc.xml"&gt;                  &lt;target name="build-doc" /&gt;                &lt;/ant&gt;              &lt;/tasks&gt;            &lt;/configuration&gt;            &lt;goals&gt;              &lt;goal&gt;run&lt;/goal&gt;            &lt;/goals&gt;          &lt;/execution&gt;        &lt;/executions&gt;        &lt;dependencies&gt;          &lt;dependency&gt;            &lt;groupId&gt;org.apache.ant&lt;/groupId&gt;            &lt;artifactId&gt;ant&lt;/artifactId&gt;            &lt;version&gt;1.8.1&lt;/version&gt;          &lt;/dependency&gt;          &lt;dependency&gt;            &lt;groupId&gt;org.apache.ant&lt;/groupId&gt;            &lt;artifactId&gt;ant-launcher&lt;/artifactId&gt;            &lt;version&gt;1.8.1&lt;/version&gt;          &lt;/dependency&gt;          &lt;dependency&gt;            &lt;groupId&gt;org.apache.ant&lt;/groupId&gt;            &lt;artifactId&gt;ant-nodeps&lt;/artifactId&gt;            &lt;version&gt;1.8.1&lt;/version&gt;          &lt;/dependency&gt;          &lt;dependency&gt;            &lt;groupId&gt;xalan&lt;/groupId&gt;            &lt;artifactId&gt;xalan&lt;/artifactId&gt;            &lt;version&gt;2.7.1&lt;/version&gt;          &lt;/dependency&gt;        &lt;/dependencies&gt;      &lt;/plugin&gt;    &lt;/plugins&gt;  &lt;/build&gt;</code></pre>  </div>
