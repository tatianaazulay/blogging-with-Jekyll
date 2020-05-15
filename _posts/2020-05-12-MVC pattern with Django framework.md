---
layout: post
title: MVC pattern with Django framework
date: 2020-05-12 02:29 -0400
description: " Model-View-Controller"
author: tatiana_azulay
---
<p>Every software has an architecture which specifies its basic structure. <br/>
Small applications may not explicitly specify their architecture but for large systems architectural design is an important step.<br/>
Architectural style is like a style of the building.</p>
There are some types of architectural styles with examples:<br/>
1) Pipes-and-filters: Compilers. The consecutive filters perform lexical analysis, parsing, semantic analysis, and code generation.<br/>
2) Event-driven: Notification services<br/>
3) Client-server: Online applications such as email, document sharing and banking<br/>
4) MVC: Web frameworks such as Django and Rails <br/>
5) Layered: E commerce web applications<br/>
6) Database-centric: inventory management software<br/>
Etc…<br/>
<strong>MVC (Model-View-Controller)</strong> is a popular way of organizing GUI apps where we can implement several views. <br/>
<strong>The main idea is to separate the data from the display.</strong><br/>
If you work on projects with Django framework, you’ll be able to practice working with MVC pattern. <br/>
Though Django uses a little bit different terminology it follows main concepts of MVC. 
Django uses Templates instead of Views and Views for Controller.<br/>
Below is the example of the MVC structure of my Django blog project.<br/>
<strong>Model</strong>
<img src="{{'/images/model.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<strong>View</strong>
<img src="{{'/images/view.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<strong>Controller</strong>
<img src="{{'/images/controller.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>



