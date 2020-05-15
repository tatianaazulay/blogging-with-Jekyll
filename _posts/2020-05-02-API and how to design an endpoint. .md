---
layout: post
title: API and how to design an endpoint 
date: 2020-05-02 02:29 -0400
description: "what needs to be considered when designing an API endpoint?"
author: tatiana_azulay
---
<h3>API and how to design an endpoint </h3>
<p>Application programming interface (API) is an interface which is used to exchange data between computers without human interference. API describes the ways and rules which can be used for interactions between computers, such as set of classes, structures, methods, functions etc…</p>
<p>For example, many web apps nowadays allow users to log in with their existing, for example, Facebook accounts instead of registering new usernames and passwords. This means that a third-party site sends an API request to Facebook login API services to check if the person is already logged in with his/her Facebook account and if not, this third-party app will redirect the user to a Facebook log-in page in order to let Facebook verify the info about the person and share some public data about him.</p>
<p>The API request is also called <strong>URL request </strong>as the client is linking to a specific URL on the server which provides an access point. The data which is sent back to the client is called a <strong>response or resource</strong>.</p>

<p>Usually API documentation describes all parts of the API such as:</p>
<p><strong>endpoints</strong>, which indicate how to access the resource</p>
<p><strong>methods</strong>, which indicates allowed methods (CRUD: POST (create), GET (read), PUT (update) and DELETE (delete))</p>
<p><strong>headers</strong>, which are sets of colon-separated name-value pairs with meta-data associated with the API request and response such as: message encoding, name and version of the browser, address from the client came from (referrer), etc.</p>
<p><strong>data</strong> (or body), which is usually a JSON file with the requested information.</p> 
<h3>So, what needs to be considered when designing an API endpoint?</h3>
Here is an example of the endpoint:

<img src="{{'/images/api.png'| prepend: site.baseurl}}" alt="" class="img-fluid" alt="Responsive image"/><br>

<h3>Structure of the endpoint</h3>
<p>The endpoint shows the entire path to the resource. However, in the documentation, usually the resource URL is spitted into more specific parts:</p>
<p><strong>the base path</strong> refers to the common path for the API.</p> 
<p>In the above example, the base path for youtube API is https:// www.googleapis.com/youtube/v3;</p>
<p><strong>the route to the end part of the endpoint: /search</strong><br>
A search result set will include matching video, channel, and playlist resources, unless the query is configured to include only a  specific type of resource.</p>
<p>The path is followed by <strong>query string parameters</strong> for this point:<br>
<strong>?part=snippet&q=cats&publishedAfter=2020-04-28T00:31:57Z</strong></p>

<h3>Query parameters</h3>
<p>An endpoint usually includes <strong>query parameters that define more detailed information</strong> about the representation of the resource the client requested.
For example, in the above endpoint in the query parameter we specify the date frame of the requested objects asking for videos published after April 28, 2020.
We’ll get 5 items as a response as this is a default value. According to the documentation of the youtube API, if we want a different number of resource instances, the maxResults parameter can specify this number which should be between 0 and 50.</p>
<p>Some of the parameters are <strong>required parameters</strong>, that must be identified in the documentation.
In the above request: The part parameter is required and specifies a list of one or more search resource properties that the response should include. 
Failure to include a required parameter in your request will result in 400 error.</p> 

<h3>Configuration</h3>
<p>
Some APIs are public and need less configuration. Others can require <strong>authorization credentials</strong> etc. For example, to be able to use the YouTube Data API you must get an API key and include it in the API request.</p>
<p>The API request can be sent with any programming language.</p>

