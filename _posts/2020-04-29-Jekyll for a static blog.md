---
layout: post
title: Jekyll for a static blog
date: 2020-04-29 02:29 -0400
description: "the process of deciding on which blogging software to use, how to set it up and design with Bootstrap"
author: tatiana_azulay
---
<h3>What?</h3> 
Blog

<h3>How?</h3> Jekyll site generator and Bootstrap CSS framework
<h3>Why?</h3> To share some thoughts and lessons I have learned throughout my software development studies.<br>
<p>Choosing appropriate development tools is one of the crucial steps before starting any project. Lack of experience and plenty of choices can make this process quite puzzling. Here’re my personal motivations for using Jekyll as a building software of this blog. I took into consideration development time and ease of deployment, learning curve and aimed functionality and appearance.<br>
Jekyll is a static blog-aware site generator which has a big community and plenty of templates.  On a local computer it is installed as a ruby gem and can be served through the local host. It’s simple and efficient. There’s also a github-pages gem which allows to deploy Jekyll and its dependencies on GitHub Pages. Great!</p>
<p>However, Jekyll is not really a blogging software. It is a static site generator and includes only content which can be loaded from a file (html, css, js, etc). Due to its static nature, there is no native solution in Jekyll for adding comments or any other dynamic content which, however, can be implemented with the third-party systems.</p>
<h3>Jekyll vs WordPress </h3>
<p>At some point I was looking at another great software for starting a blog such as WordPress- an open source software written in PHP and paired with a MySQL. Like Drupal and Joomla WordPress is a content management system which serves the content dynamically: retrieves the requested content from the database, applies templates, plugins, etc. and finally generates an html page. Dynamic sites can run server scripts and change content on the fly, including blog comments. However, they have some downsides as well. The main issues are security (interaction with the database makes them more vulnerable) and lower speed. I would compare static sites to quick premade meals in a supermarket and dynamic sites to meals in a restaurant which are being prepared after the order is placed.</p>
<p>While both static and dynamic sites have their strengths and weaknesses, I made my choice toward static blogging based on the criteria which were important for this project: fast and easy implementation and deployment, basic functionality and quickly customizable appearance.
The inability to serve dynamic content while using Jekyll for my static blog was compensated by multiple Jekyll advantages.
</p>
<h3>Ease of implementation </h3>
<p>Due to its static nature Jekyll can be easily set up. No dabase required. 
The main steps of Jekyll blog set-up are the following:<br>
Prerequisites: Jekyll and ruby needs to be installed.
Inside the project folder create Gemfile and index.html</p>
<img src="{{'/images/1.png' | prepend: site.baseurl}}" alt="" class="img-thumbnail mw-50" alt="Responsive image"/>
<img src="{{'/images/2.png'| prepend: site.baseurl}}" alt="" class="img-thumbnail mw-50" alt="Responsive image"/>
<p><strong>$ bundle<br>
$ jekyll serve</strong></p>
<img src="{{'/images/3.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>

<p>The directory needs to be organized in a way jekyll expects.
So the following folders needs to be created:<br>
<a href="https://jekyllrb.com/docs/layouts/" target="_blank">“_layouts”</a> which will hold templates for similar pages with different content,<br>
<a href="https://jekyllrb.com/docs/includes/" target="_blank">“_includes”</a> to create reusable components,<br>
<a href="https://jekyllrb.com/docs/datafiles/" target="_blank">"_data”</a>to include a yml file to specify configuration options,<br>
“_posts” which will hold blog posts<br>
"_sass" and <a href="https://jekyllrb.com/docs/assets/" target="_blank">"assets"</a> to hold cscc files </p>
<p>Now our folder looks like this</p>
<img src="{{'/images/4.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<p>Jekyll uses <a href="https://shopify.github.io/liquid/" target="_blank">Liquid template language</a> so we’ll use 
<img src="{{'/images/11.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
for our default.html layout.
Reusable components from _includes folder will be referenced as for example
<img src="{{'/images/22.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<br>
In the page’s <a href="https://jekyllrb.com/docs/front-matter/" target="_blank">front matter</a> we specify layout, title, permalink.</p><br>
<img src="{{'/images/55.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>

<p>$ jekyll new post Post#1 
will automatically create a post with the title Post#1</p>

<h3>Bootstrap for a better look</h3>
<p>Jekyll community provides plenty of design themes which can be downloaded or installed as gems. However, I decided to integrate bootstrap into Jekyll project and use favorite bootstrap elements to get the desired appearance of the blog.<br>
By default Jekyll looks for sass files in _sass folder. So we need to create  _sass folder in our main directory and import the bootstrap scss there. <br>
In _variables.scss we can overwrite bootstrap variables to customize the site and in _main.scss we need to import variables before bootstrap:<br>
@import "variables";<br>
@import 'bootstrap/bootstrap';<br>
Under /assets/css/  we create styles.scss file for adding pure css styles for the blog.</p>


<h3>Conclusion<h3>
Jekyll provides plenty of tools to build a functional static blog. 
As Jekyll builds static websites from dynamic components it is also a great practice to use templates, 
markdown,partials etc.
 
