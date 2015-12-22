Config Options see: org.apache.catalina.valves.AbstractAccessLogValve

```xml
<Host name="localhost"
                 appBase="webapps"
                 unpackWARs="true"
                 autoDeploy="false">
               <Valve className="de.is24.tomcat.StdoutAccessLogValve"
                      pattern="%h %l %u %t &quot;%r&quot; %s %b"/>
</Host>
```
