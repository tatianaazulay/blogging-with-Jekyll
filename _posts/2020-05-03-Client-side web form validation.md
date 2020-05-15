---
layout: post
author: tatiana_azulay
title: Client-side web form validation 
date: 2020-05-03 02:29 -0400
description: "Keep it short, make it easy with jQuery validation plugin"
author: tatiana_azulay
---
<h3>Client-side web form validation</h3>

<p>While designing a web form intended to collect data from users there are a lot of aspects to be considered regarding the form’s UI, its interactivity and content, ability to catch input errors etc. 
The most popular approaches to form designs are:</p>
1. keeping them short (only include concise and necessary questions) and
2. helping the user to fill them in.
<p>The latter deals mostly with form validation and input masking.
<strong>There are 2 types of validation: client-side and server-side.</strong>  Validation is the process of checking if the data is in acceptable format. Verification is the process of checking if the data is correct (for example, running the credit card test charge to make sure the number is correct) and if the data is what the user intended to input (password verification).  </p>
<p>Server-side validation is necessary before any verification and is done after the form is submitted when the server can send back an error message.</p>
<p>Client-side validation is done by the browser and makes it faster to catch the input errors than waiting for the server to send back a response. The disadvantage of the client-side validation is that it is not supported uniformly among all the browsers and devices and it is hackable (easy to bypass).</p>
<p><strong>There are 2 types of client-side validation: built-in browser validation and inline validation when the user gets feedback while filling out the form before clicking submit.</strong></p>
<p>Inline validation plays a big role in user experience design and can make the process of filling in the form much easier.</p>
<p>Below is an example of using jQuery validation plugin for basic payment form fields.</p>
<strong>Include the jQuery library and the jQuery validation plugin. Use CDN or download them</strong> 
<img src="{{'/images/cdn.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<hr>
<strong>In HTML specify the elements to be validated. They need to have id attributes</strong>
<img src="{{'/images/html.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<hr>
<strong>Create the Validation Rules</strong> 
<img src="{{'/images/rules.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<hr>
<strong>Create error messages</strong>
<img src="{{'/images/message.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/>
<hr>
<h3>Jquery is an easy and effective way to implement inline validation for greater user experience.
Full documentation can be found at <strong><a href="https://jqueryvalidation.org/documentation/">https://jqueryvalidation.org/documentation/</a></strong></h3>


