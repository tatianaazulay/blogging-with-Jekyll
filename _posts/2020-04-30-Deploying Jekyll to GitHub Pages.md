---
layout: post
title: Deploying Jekyll to GitHub Pages
date: 2020-04-30 02:30 -0400
description: "_CONFIG.YML and Project Page URL Structure/Soft coded links "
author: tatiana_azulay
---
<p>Due to its static nature Jekyll has many deployment possibilities.
I was interested to deploy Jekyll blog to GitHub Pages by using github-pages gem.
The process of deploying a Jekyll site to gh-pages is like deploying any other static site.
For that you create a project repo on GitHub, push all your project files to the master branch and then create a gh-pages branch. GitHub by default will automatically generate your static site directly from the gh-pages branch.</p>
<p>However, there are several steps which can’t be missed while deploying Jekyll:</p>
<ul>
<li>First of all, add gem 'github-pages' to a Gemfile. This gem is provided by GitHub and used to manage Jekyll and its dependencies on GitHub Pages. </li>
<Li>Then we need to work on the project url structure and _config.yml file which tells Jekyll basic info about our project.</li></ul>
<h3>_CONFIG.YML</h3>
<p>YAML is known as “a human-readable data-serialization language” which is used for configuration files and for storing or transmitting data.</p>
<p>Yaml uses maps (Hashes, Objects, Dictionaries), sequences (arrays, lists) and scalars (Strings, Numbers, Values).</p>
<p>The basic syntax and logic used by Yaml is the following:</p>
<ul><li>Key/value in a map is divided by the colon followed by a whitespace (space or newline)(: ).</li>
<li>The value can be a scalar (string or number), map or a sequence.</li>
<li> Sequences indicate each entry with a dash and space ( “- ”).</li>
</ul>
<p>See the full <a href="https://yaml.org/spec/1.2/spec.html" target="_blank">YAML</a> specification for more information.</p>

<p>Jekyll looks for .yml or .json files,  another data serialization language, in _data folder under the main directory. </p>
<p>According to the described above Yaml syntax we should specify the following in our _config.yml:<br>
<strong>url: [GITHUB ACCOUNT NAME]<br>
baseurl: [REPO NAME]</strong></p>

<img src="{{site.baseurl}}/images/yml.png" alt="" class="img-fluid" alt="Responsive image"/>
<p>
As we set baseurl: /Jekyll-blog-with-Bootstrap, Jekyll considers /Jekyll-blog-with-Bootstrap/ as the root of the blog and will serve it locally at <br>http://localhost:4000//Jekyll-blog-with-Bootstrap / <br>
As we set baseurl: /Jekyll-blog-with-Bootstrap, Jekyll considers /Jekyll-blog-with-Bootstrap/ as the root of the blog and will serve it locally at http://localhost:4000//Jekyll-blog-with-Bootstrap / <br>
Now url and baseurl keys can be used for handling url paths inside the blog.
</p>
<p>
As Jekyll uses Liquid markup, so we need to use double curly braces to output content of our keys. We use double curly braces to reference info which is passed to the html.<br>
Thus,to access styles.css file which is located in css folder under assets directory we need to prepend baseurl to its relative path <br><strong>href="{{'/assets/css/styles.css' | prepend: site.baseurl }}".</strong> We can also write it this way: 
<strong>href="{{ site.baseurl }}/assets/css/styles.css"</strong>
The result link will be <br><strong>https://tatianaazulay.github.io/Jekyll-blog-with-Bootstrap/</strong>
Thus,to access styles.css file which is located in css folder under assets directory we need to prepend baseurl to its relative path <strong>href="{{'/assets/css/styles.css' | prepend: site.baseurl }}".</strong> We can also write it this way: 
<strong>href="{{ site.baseurl }}/assets/css/styles.css"</strong>
The result link will be <strong>https://tatianaazulay.github.io/Jekyll-blog-with-Bootstrap/</strong>
</p>
<h3>Conclusion<h3>
Instead of using hard code links in the blog and write them in the source code, we implemented soft code links.<br>
Yaml and Liquid markup used by Jekyll allows us to soft code links inside the blog which is extremely helpful when we move projects to different locations. The values of url and baseurl keys are defined in _config.yaml file and referenced with doble curly braces from different pages of the project. The same technique is also used in constructing dynamically generated links in dynamic website, as for example for soft coded links generated from a search result.
