---
layout: subject
title:  "Web Application Security Security > XSS"
date:   2014-04-25 16:54:46
author: Quinten De Swaef
categories:
- documentation
tagged: webapp, xss
permalink: /learn/subjects/web-application-security/xss
---

##What?
Cross Site Scripting (XSS) is an input validation issue that lets attackers run code in your browser within the trusted context of a site that you’re visiting.
Browser scripting code can do quite a bit, including sending your authentication cookies to a malicious site so they can be used to impersonate you.

##How?

Most of the times, XSS manifests itself in about 4 different ways.

* Reflected XSS
* DOM-Based XSS
* Persistent XSS
* Blind XSS

  <h3>Reflected XSS</h3>

  Reflected XSS is a form of Cross Site Scripting that happens when an attacker is able to inject arbitrary code into a web page and the server reflects it back to the victim. In most cases, this arbitrary code is injected into an url. Making the victim click the url will <b>reflect</b> the code back to the victim's legitimate webpage.  

  <h3>DOM-Based XSS</h3>

  DOM-based cross site scripting is very much like reflected XSS because it also <b>reflects</b> your payload back to the victim by injecting the arbitrary code for example in the URL. The main difference is that DOM-based XSS doesn't pass the server. DOM-based XSS relies on the fact that existing javascript code fetches arguments from the url and uses it before sanitation takes place.

  <h3>Persistent XSS</h3>

  Persistent XSS is an attack that is in most cases far more dangerous than traditional Reflected or DOM-based attacks. It relies on the fact that your payload gets stored or <b>persisted</b>, for example in a database. The attacker then only has to rely on the fact that a victim has to visit the page containing the stored XSS, for example in a public profile page.

  <h3>Blind</h3>

  Blind XSS is a form of Cross Site Scripting which is far harder to execute, but can yield far better results when it comes to exploiting private systems or backoffice software.

  In Blind XSS, the attacker will exploit a form of stored XSS, containing a payload that can **notify** him when the XSS is triggered. Using Blind XSS, an attacker wants to exploit other systems which may rely on the data that is entered by the user, for example an admin page. It's a known fact that administration pages or other, more private systems are less secure, because of the fact that they are not publicly accessible. Therefore, it's far more likely that a non-public page would "forget" to sanitize user-inputted-data.

  This form of Cross Site Scripting is called blind XSS, mainly due to the fact that the attacker cannot instantly see whether any of the third party systems (if there are any) are vulnerable.

<div class="row"></div>


##Attack Vectors

###Session Hijacking

###Defacement

##Countermeasures

Countering XSS vulnerabilities boils down to just one thing: **input sanitation**
