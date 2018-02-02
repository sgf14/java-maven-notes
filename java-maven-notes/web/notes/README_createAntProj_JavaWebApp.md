documents steps to create a Java EE project and use ant to build the war file.  Alternative to this is a creating a Maven Project.
Jul16- initial project using ant build was custSuptBasic2.  will be expanding this file as part of JWA reading.

1) With Java EE perspective selected choose File/New/Dynamic Web Project
2) 1st page- enter project name- no spaces.  leave rest at default.  ensure you leave at default dir. hit next
3) 2nd page- leave defaults (src dir), hit next
4) 3rd page- select checkbox create WebContent dir, hit finish
--new project is built--
5) create build.xml file under WebContent dir for Ant build.  
		NOTE [project]/Properties/Java Build Path/Source-Class path at bottom of window MUST match your build.xml build path (default  		on Dynamic Web Project is /build/classes)  or the project wont find the java classes in order to run in the webpage.
6) create index.jsp file under WebContent dir
7) src dir will be under Java Resources folder, can add packages and java files as needed
8) web.xml will be under WEB-INF folder under WebContent along with META-INF folder

Add external Jar Library dependencies- see notes below for details
1) find/download jar file.  I have saved these up in C:\users\documents\coding\jarLib
2) click on project, right click, select properties
3) go to Java Build Path, then Library tab
4) click add External Jar button, find file and click ok.  Jar is added to project under Java Resources/Libraries and is available for use. This make jar available for use within the class files.
5) copy a 2nd copy of the jar file to the WEB-INF/lib directory in Explorer and refresh project.  This allows jar file to be accessible when running the war file on the server.  build.xml file had to be altered to allow WEB-INF/lib to be part of class path.  See <patternset> <path> and <compile> targets.  Used coPid build.xml as a model.
6) Note you have to run build/clean target if you already have a war file created, otherwise build will fail.  should probably change build.xml to make clean a dependancy for init target.
7) Note 2


Build and Deploy the project
1) after build.xml is created right click on build.xml then Run As/ Ant Build.  after you run it once it will also show up under the toolbox icon at the top
2) right click project and Run As/Run On server, select Tomcat 8 and project will run the war file

Details
1) War step- During build.xml file creation.  in header make sure default="war" if you leave it as "compile" or some other prelim step the war file creation will not occur.  In custBasicSupt2 project the ware file is left at the base WebContent Dir.
2) Clean Step- To Run Clean (deletes /build and war file) Select Run as then 2nd Ant Build( the one with the ellipsis ...)  this allows you to select options to run within the build.xml.
3) src- you can add packages subsequent to project creation, as needed
4) WebContent- all jsp's, .js, non-java files will exist in this dir
5) build.xml contents- used a combination of Learning Java (LJ) pg 581 and coPid build.xml to create the build.xml in custSuptBasic2 (custSuptBasic had started with File/New/Enterprise Application Project- and that really wasnt what I wanted.  deleted this after successful creation adn Ant deployment of custSuptBasic2 project, per steps above.  07/04/16.
6) see note above about default build path.  the build.xml file build path MUST match the path the project has designated- or java  .class cannot be found and you will get a HTTP 500 error (..java class not found...)

Ant build- Adding Jars/third party Libraries
1) Had to do this first with javax.servlet-3.1.jar.  the basic web project creation does not include this jar (its javax...).  Java Extension.
2) Note the project has to be setup as a Java project (small J above folder).  Otherwise there is no Java Build Path selection.  In the case of coPid the jars have to be added manually in the WEB-INF/lib folder.  Still a little unsure of exact process- talk with Carol E.
3) the steps above are taken care of in Maven projects using the POM <dependency> method. and the jar file itself is housed in the .m2 directory.  Part of what maven does above and beyond Ant is this type of dependency management.
4) Source for jar file downloads Java2s = http://www.java2s.com/Code/Jar/CatalogJar.htm or Maven Repository= (same place as Maven dependencies = https://mvnrepository.com/  . Often it is best to search google however with the name of the jar you are looking for.

Finding useful 3rd party libraries generally
1) Java Cookbook- pg 44
2) sourceforge.net, grepcode, maven repository, apache software foundation
3) Java web app book has tons of used examples (in the form of maven dependancies) Still reading through book.

