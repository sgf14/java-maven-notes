06/12/16:  Documents differences in Apache Ant build and Apache Maven builds for Java Web applications. Creating notes for later 
reference.
	Ref: see Java Web Apps book- chap 2 and 3-Maven. and Learning Java Book, chap 15, and partial chap 14- for Ant.
	
1) Ant build is the predecessor of Maven.  Both Ant and Maven create java .WAR files for Java web app deployment on a webserver.  The Application server that opens this war file can be Tomcat, JBoss, Glassfish or WebLogic, etc.  And will either be localhost for dev or on the production  web server.
2) Ant- Ant automates the javac and packaging of the project into a war file.  A good explanation is offered in LearingJava, chap 15, pg
  581.  All these steps could be done manually, but that is a pretty ineffective way of building a project.
    a.  build.xml is the file within each project that holds the ant build directives.
    b.  war file in typical project is under the base dir of the project.  in PID, Jae changed this to the root of the build dir.
3) Maven- Adds a layer of project mgmt on top of Ant to further automate the process of creating a java web app, but still as an end 
  result creates a .war file that the java app server uses to deploy the project. Its big benefit is better project mgmt and life cyle
  of a web app. Maven actually uses Ant for the war file creation itself (as a plugin) and has a very similar XML style structure.
    a.  pom.xml is the file- equivalent to Ant build.xml- within each project that holds the directives.
    b.  the 'effective POM' tab (once the pom file is opened) lists the full details and file source/target structure.
    c.  war file by default is under the base Target directory.
4) Usage- either one offers an effective method of building java projects, although Maven is more commonly used as the projects grow
  larger and more advanced.
  
5) War/Jar-  both JAR and WAR files are simply zipped files, similar to .TAR files.  Jar files are packaged to be used as library type files to extend the 
base capability of java.  for example there is a jdbc.jar used to connect to Oracle databases, or Log4J.jar and SNMP.jar etc.  See 
PID for a multitude of extensibility used by that application.  Where as war files are the same thing but used to package web applications along with some deployment info. see chap 15, pg 539 of LearningJava book for a good explanation.