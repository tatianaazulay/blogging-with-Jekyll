---
layout: post
title: Continuous Integration and Build 
date: 2020-05-01 02:29 -0400
description: "automate the build and testing of code after each commit"
author: tatiana_azulay
---
<p>Even when you work by yourself on several branches of one project there is a possibility of some conflicts while merging the changes. The merging issues are much more serious when many developers work on one project simultaneously and do not integrate their code frequently.</p>
<p>Continuous (frequent) integration is the key to avoid merging conflicts and always have the testable code that compiles. Because it takes too much time and effort to integrate all the changes and make sure they work, automation of this process is done with the build.</p>
<h3>So, what is the Build?</h3>
<p>Build is not just code compilation, it is a set of activities to generate, test and deploy software. There are a lot of different types of builds: incremental builds, scheduled builds, release builds etc.<p>
<p>Usually build cycle includes such steps as </p>
<ul><li>compile</li>
<li>test</li>
<li>deploy</li>
</ul>
<p>but phases of the build cycle depend on the type of the build and on its complexity, as, for example, large and complex software requires longer and more complicated builds. All the steps of the build are described in build files, which are called also configuration files or jobs. A popular build file developed in 1970s was the Makefile, a classic Unix build tool.</p>

<p><a href="https://en.wikipedia.org/wiki/List_of_build_automation_software" target="_blank">Automated build process</a> is the core element of the continuous integration, a development practice which aims to trigger the automated build and testing processes after each code change commit.</p>

