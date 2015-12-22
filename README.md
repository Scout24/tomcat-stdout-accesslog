[ ![Download](https://api.bintray.com/packages/immobilienscout24/maven-oss-releases-repo/tomcat-stdout-accesslog/images/download.svg) ](https://bintray.com/immobilienscout24/maven-oss-releases-repo/tomcat-stdout-accesslog/_latestVersion)

Config Options from: org.apache.catalina.valves.AbstractAccessLogValve

<p>Abstract implementation of the <b>Valve</b> interface that generates a web
server access log with the detailed line contents matching a configurable
pattern. The syntax of the available patterns is similar to that supported by
the <a href="http://httpd.apache.org/">Apache HTTP Server</a>
<code>mod_log_config</code> module.</p>

<p>Patterns for the logged message may include constant text or any of the
following replacement strings, for which the corresponding information
from the specified Response is substituted:</p>
<ul>
<li><b>%a</b> - Remote IP address
<li><b>%A</b> - Local IP address
<li><b>%b</b> - Bytes sent, excluding HTTP headers, or '-' if no bytes
    were sent
<li><b>%B</b> - Bytes sent, excluding HTTP headers
<li><b>%h</b> - Remote host name (or IP address if
<code>enableLookups</code> for the connector is false)
<li><b>%H</b> - Request protocol
<li><b>%l</b> - Remote logical username from identd (always returns '-')
<li><b>%m</b> - Request method
<li><b>%p</b> - Local port
<li><b>%q</b> - Query string (prepended with a '?' if it exists, otherwise
    an empty string
<li><b>%r</b> - First line of the request
<li><b>%s</b> - HTTP status code of the response
<li><b>%S</b> - User session ID
<li><b>%t</b> - Date and time, in Common Log Format format
<li><b>%t{format}</b> - Date and time, in any format supported by SimpleDateFormat
<li><b>%u</b> - Remote user that was authenticated
<li><b>%U</b> - Requested URL path
<li><b>%v</b> - Local server name
<li><b>%D</b> - Time taken to process the request, in millis
<li><b>%T</b> - Time taken to process the request, in seconds
<li><b>%I</b> - current Request thread name (can compare later with stacktraces)
</ul>
<p>In addition, the caller can specify one of the following aliases for
commonly utilized patterns:</p>
<ul>
<li><b>common</b> - <code>%h %l %u %t "%r" %s %b</code>
<li><b>combined</b> -
  <code>%h %l %u %t "%r" %s %b "%{Referer}i" "%{User-Agent}i"</code>
</ul>

<p>
There is also support to write information from the cookie, incoming
header, the Session or something else in the ServletRequest.<br>
It is modeled after the
<a href="http://httpd.apache.org/">Apache HTTP Server</a> log configuration
syntax:</p>
<ul>
<li><code>%{xxx}i</code> for incoming headers
<li><code>%{xxx}o</code> for outgoing response headers
<li><code>%{xxx}c</code> for a specific cookie
<li><code>%{xxx}r</code> xxx is an attribute in the ServletRequest
<li><code>%{xxx}s</code> xxx is an attribute in the HttpSession
<li><code>%{xxx}t</code> xxx is an enhanced SimpleDateFormat pattern
(see Configuration Reference document for details on supported time patterns)
</ul>

<p>
Conditional logging is also supported. This can be done with the
<code>conditionUnless</code> and <code>conditionIf</code> properties.
If the value returned from ServletRequest.getAttribute(conditionUnless)
yields a non-null value, the logging will be skipped.
If the value returned from ServletRequest.getAttribute(conditionIf)
yields the null value, the logging will be skipped.
The <code>condition</code> attribute is synonym for
<code>conditionUnless</code> and is provided for backwards compatibility.
</p>

<p>
For extended attributes coming from a getAttribute() call,
it is you responsibility to ensure there are no newline or
control characters.
</p>

```xml
<Host name="localhost"
                 appBase="webapps"
                 unpackWARs="true"
                 autoDeploy="false">
               <Valve className="de.is24.tomcat.StdoutAccessLogValve"
                      pattern="%h %l %u %t &quot;%r&quot; %s %b"/>
</Host>
```
[![Build Status](https://travis-ci.org/ImmobilienScout24/tomcat-stdout-accesslog.svg?branch=master)](https://travis-ci.org/ImmobilienSc````out24/tomcat-stdout-accesslog)

