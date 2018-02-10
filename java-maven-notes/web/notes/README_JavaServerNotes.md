05/28/16
Purpose: documenting the findings about the setup for Java server for web apps.  See notes written in Java for Web Apps book- Chap 
 2 and 3.  These cover the server setup parts you have to do in the beginning to load the book downloaded projects and get them     
 running in Eclipse. There is some detail, but many parts it assumes the user already knows the information, in order to save space 
 in the book.  Had to do independent learning
 in order to figure out how to get this working and it took about 2 weeks to get it working.
 hopefully this will help when you need to do the setup again in future

1) One time setup vs running a project- this doc focuses more on the initial Tomcat setup w/ maven vs starting a project on the server. See README_runMavenProjInst.md for startup steps for running an project. 

2) Server startup: Java server start is a different approach.  Unlike PHP/XAMPP or jsNode you start the server by right clicking
   the project and Run As/Run on server then pick the server to run on (tomcat 8 for book examples)
   ; instead of starting the server first

3) Tomcat/Eclipse: Tomcat is the server recommended in the book and XAMPP (while it does work) only supports Java 7, not 8.  So
	downloaded tomcat from Apache per Chap 2 and got it working.  CLI works ok, but cant do debug function like you can  
	from the tomcat container within Eclipse.   see notes written in book.  this took a while to setup.  but mainly because
	I was trying to start the server first, then the project.  For Java you need to do it the other way around- see 1) above.
	the book doesnt really talk about this.
	Other Java Servers: See chap 2 some other popular Java servers are JBoss (now Wildfly), Glassfish, WebSphere and WebLogic.
	
	
   Servers are split into two categories:
	1) Web Server: (tomcat) More basic level webserver supporting http to the client, typically via servlet method.
	2) Application server: (Glassfish, Weblogic, tomee, etc) more advanced server function that in addition to http, exposes more of 
	the business logic and functionality to the client, including engrained security and EJB- Enterprise Java Beans.  
	tomee is the application server version of tomcat webserver.  
	Here is a good explanation: https://www.javaworld.com/article/2077354/learn-java/app-server-web-server-what-s-the-difference.html
	

3) Tomcat CLI: The CLI tool is run from the command line and is used to start the server independent of Eclipse.
	a) during the testing problems with Eclipse the CLI startup/shutdown.bat 's always worked to start the localhost
	server.  Can still use this to deploy a compiled War file, only downside is that you cant enter 'debug' mode (run as Debug)
	for testing purposes.  Its easy to use.  See chap 2- there is some initial .xml file changes that need to be doen
	when you initially download the app, but its pretty straightforward.

4) Maven: Book doesnt talk much about maven- it assumes knowledge of the app.  See youtube video bookmarked in Firefox/Maven folder
  there is a good tutorial on how to use Maven from both CLI and within Eclipse (m2e).  I did not download Maven independently
  the Eclipse plugin version works pretty well- so I cant use the CLI version.  work is done in eclipse.
	a) Import Book project as type maven. do File/Import then follow steps.  to view in Java EE Working Set, make 
	  sure you select that in the pulldown.  Make sure the POM displays.
	b) ONE TIME- To compile Project you need to have Window/prefs/Java setup as jdk, not jre- NOTE there is also a subfolder here that has
	  to match.  It will not compile otherwise.  I kept the jre and added a new jdk, and selected its checkbox
	c) Clean Install- to compile a project when java files are changed right click proj/Run/then Maven Clean followed
	  by Maven Install.  Clean deletes the old stuff, Install re-compiles .war file.
	 d) Other (Java) build automation tools: Gradle and Apache Ant/Ivy are other products that perform some similar functions.  See Java Cookbook (JC) chap 1 pg 22-29 related to Ant/Maven/Gradle

4) JAVA_HOME: Note on this laptop you have 2 Java sets- one in the Program Files and another in Program Files (86x).  the 
  Program Files one is more up to date and is what Eclipse is pointing to (8-0-35 at time of writing).  In Windows
  Explorer/right Click on PC, Advanced/Envronmental Varialables.  need to make sure JAVA_HOME is pointed to the right one
  .  Was pointed at (86x) one and had to change it.  
  a) Full Access- Note also that in explorer the Apache folder that holds Tomcat has to have full write privleges in
    order for Tomcat to run.  Otherwise you get a 500 unauthorized webpage when you enter http://localhost:8080/.