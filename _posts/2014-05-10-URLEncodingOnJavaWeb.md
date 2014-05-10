---
layout: post
title: Http Encoding Charset on Java Web
---
Charset and Encoding on Java Web Server
================================================

 HTTP Request
-------------------

Two parts in a http request is related to charset: URL and body content. 

* Domain name

	Domain name is using subset of ASCII, and any locale domain name will be transformed into the subset by [punnycode](http://en.wikipedia.org/wiki/Punycode). punnycode only accept unicode string, so any other charset characters will be converted to unicode first.
	
	For Web Server, first convert the International domain name to punnydoe encoded name, then just set the host to converted string for supporting International Domain Name, [such as Jetty](http://wiki.eclipse.org/Jetty/Howto/Configure_Virtual_Hosts#Configuring_Virtual_Hosts_with_Non-ascii_Characters).

* URL

	URL only using ASCII charset, any characters outside the ASCII charset must be converted into valid ASCII format. Details in [W3School: URL Encoding](http://www.w3schools.com/tags/ref_urlencode.asp).
	
	Url encoding can accept different charset characters, so there are some problems as decoding the URL string using default charset in Java Web Server, e.g. Tomcat use ISO-8859-1, Jetty use UTF-8. There are two common ways to get right decoded query string:
	
	>+ Specify url encoding charset on server configure file, e.g. in Tomcat's server.xml add **URIEncoding="UTF-8"** attribute in _connector_ element
	>+ Tell Java Web Server using charset value in content-type, e.g. set the useBodyEncodingForURI attribute on the <Connector> element in server.xml to true for Tomcat.
	>+ Or specify url charset before decoding URL, e.g. in jetty using specific Jetty Api *setQueryEncoding* or just call call `javax.servlet.ServletRequest.setAttribute("org.eclipse.jetty.server.Request.queryEncoding", "xxx")`
	>+ Or convert the wrong decoded string back bytes, then constuct new string with right encode, i.e. `new String(request.getParameter("**").getBytes(8859_1),"UTF-8") `
	>+ or use `URLDecoder.decode` to decode the original url or query string
	>+ The HttpServletRequest specification says (without any logic, AFAICT):
		+ getContextPath: not decoded
		+ getPathInfo: decoded
		+ getPathTranslated: not decoded
		+ getQueryString: not decoded
		+ getRequestURI: not decoded
		+ getServletPath: decoded
	>+  more see
		+ [Tomcat FAQ: CharacterEncoding](http://wiki.apache.org/tomcat/FAQ/CharacterEncoding)
		+ [Jetty Howto: International Characters](http://wiki.eclipse.org/Jetty/Howto/International_Characters)

* HTTP Request Body

	Should set charset in content-type tell server the charset of the content.

HTTP Response
------------------------

+ Should set charset in content-type, in servlet `response.setContentType("text/html;charset=utf-8");` 
+ Or use `response.setCharacterEncoding("**");`, it may make browser or http client to guess wrong charset if without setting charset in content-type
