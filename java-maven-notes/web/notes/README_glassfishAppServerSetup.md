Was able to download and establish Glassfish Application Server in Jan 2018.  See C:glassfish5 folderset and base level readme file.

Ignore the glassfish3 folder.  this was an initial attempt that didnt work.

Online in the Oracle technet, middleware glassfish website found that I had to get over to the java EE 8 
downloads section and get glassfish from there.  Once there- see link below- Clicked on the righthand side 
under java SDK and downloads.  there is a java 8 and glassfish (5) download.  that is the link I clicked.
the initial glassfish 3.1 page didnt work.  I think becasue the java sdk on my machine was not the rigth version

http://www.oracle.com/technetwork/java/javaee/downloads/index.html
to get the Java EE and glassfish [w and jdk download]- right hand side top, under SDK section.

so there was some trial and error here.  but server itself- see readme to launch, does work.

I have not yet setup glassfish in eclispe or launched a project- similar to tomcat.  THere is useful info
in glassfish5/glassfish/docs folder- some htmls in there.  this si the next step.

Other info:
In Java there are two basic styles of servers- the webserver and the application server.  see ..server.. readme for details
tomcat is a basic webserver, glassfish is more enterprise oriented applciation server that was forked off hte original
apache tomcat web server.  it includes some enhanced capabilities for REST, security, etc.  other app server of similar type are jboss/wildfly, weblogic, jetty, payara and several others. 