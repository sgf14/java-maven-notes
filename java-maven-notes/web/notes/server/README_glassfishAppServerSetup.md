Was able to download and establish Glassfish Application Server in Jan 2018.  See C:glassfish folder sets w/ base level readme files and notes below.

Quick Start:
1) This is for initial Glassfish server setup on LocalHost (or could be on an actual server for that matter- as the Web Application Server).
2) Once server is setup on C: drive it functions similar to Tomcat-  
  To start a project, Just Select it from the server list and run it. See MavenRun readme.
3) Validate your JDK level in Eclipse.  Eclipse Juno is JDK7- so I needed Glassfish 4.  
4) Download Glassfish from Oracle middleware website. Once zip file is downloaded I unzipped to C: drive\glassfishx [4 in this case].
5) In Eclipse: Go to Help/Eclipse Marketplace.  in search type glassfish and search.  you want Glassfish tools.  click through screens
 you have to restart Eclipse after this.
6) Eclipse: Go to Windows/Preferences/ then popup- Server then Runtime Environment new popup
7) The click Add and pick Glassfish [4 in my case] then pick your glassfish4/glassfish directory (errors must clear, then you know you
  are in the right folder]  this will allow you to get to the default domain1 for your apps.
8) Next tab- leave username as admin, leave password field blank and click finish button.
9) Run a test app- make sure it starts.  This process worked with j2ee-design project on the Glassfish4 Application server.  It also still 
  works with Tomcat Web container.  They both default to http port 8080 so you cant have them both running at the same time w/o changing
  admin properties.


Details/Notes:
1)x
2)x
3) Ignore the glassfish3 an 5 folders for now.  3= jdk6 and 5=jdk8.  But Eclipse Luna [current Eclipse version is setup to support JDK7].
4) I actually downloaded Glassfish 4 from Payara site- it happened to be the link on Google search that came up forst.  I tested the download and the zip file worked ok.
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