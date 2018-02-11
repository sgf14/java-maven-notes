Purpose: This is written as a reminder of how to create a new Java web app projects in Eclipse using Maven as the builder.  Used in conjunction with Java for Web Applications (JWA), mainly chapter 2.  Have another README set for Ant build tool projects.  Maven is the preferred build tool in JWA.  Ant is described briefly in Learning Java (LJ) book.  see README_createAnt.. file for corresponding Ant instructions.

Maven Quick Ref for new project creation:
1) File/New/Project/Maven.  1st tab click 'no archetype' radio, keep default workspace/add to Java EE working set
	2ndd tab- add group id 'com.prod', artifact = '[project name you want]' Pick WAR file as type then finish.  See below
2) Make sure a Deployment descriptor & Java Resources folder  got created (see past projects for standard tag set).
	At this point you should also be able to right click on the propject and see Run/Run On server selection.
3) Add com.prod [or equivalent] java base package under src/main/java.  IN Java Resources, NOT in src folder- wont add as java 
	package otherwise. 
4) Instantiate an initial java class file under base level package [prod].  ie HelloWorld.java as a start and to test server
5) In folder set [not java] open src/main/webapp folder. Create a web/WEB_INF folders for jsp/css/js files- 
	see below for archetype above notes.  Havent figured out an archetype that has base level 'web' folder.
6) Add web.xml file under base web/WEB-INF folder, and populate with basic details- see past projects
7) Add index.jsp file to 
8) Update POM
	- add base http servlet dependencies
	- add build/plugin basic tags
	- add web folder ref to maven plugin set** note this would only be if you can get base project 'web/' folder to work
		otherwise default src/main/webapp folder- this is not needed. 
9) Select project, right click, run as Maven install.  make sure it gets through build.  
	- if not make alterations, then clean, then install
10) Run/Run On server: test make sure hello world html displays in mozilla (default browser on tomcat 8) 
	This gets a basic project up and running.  but you also have to have webserver loaded (tomcat, tomee, jboss, jetty etc)
11) Logging.  For Larger project add this the following basics. Apache log4j2 typcial- see logging readme for details
12) MVC.  Spring typical.  See spring mvc readme for details. 
	
Details/Steps:
1) Will house the non-imported book examples under base workspace directory.
      1.1) All projects go under the Eclipse workspace base dir.  Each maven project has to have its own folder/head- you cant nest them 
      one within the other.
      --
      1.2) Archetypes/No Archetypes: if you use the archetype function then you cant re-arrange any of the base folders.  If you pick
      no archetype selection then the packaging- on next screen- has to be a WAR file, not a JAR file- if you want it to be a web
      project.  I like having the web/js files being under the base level project, vs under the src package, so have selected 
      no archetype on many recnet projects.  TGhe downside obviously is you have to manually create more stuff.  Archetypes
      are ment to eliminate some of this manual work. More detail is below w/ older notes sections.
      	1.2.1) Archetype examples:
      	have used artifact maven-archetype-webapp and maven-archtype-j2ee from Apache- those work well enough except the webapp
      	folder thing described above.
      	1.2.2) in the xx-webapp one I had to create the source folders- do this by create src/main/java in Java Resources- properties then 			Java Build Path, then Sources then	1st line select and Add Folder.
			this creates the standard 4 java packages [folders].  Make sure normal java package icon shows up and not a folder set.
	  --
      1.3) Even though you cant create a folder subfolder struct you can easily expose/hide projects w/i a perspective (Java EE) 
      using the Project Explorer/View menu icon (small down arrow) then 'Edit Active Set' and pick the projects you want to see 
      to avoid clutter.
      --
      1.4) Web folder.  This particular no & archetype creates a 'src/main/webapp' folder and index.jsp under src/main.  I have not yet
      found an archetype that has a base project level 'web' folder like the Java for Web Applications book.  For now just need to have
      js/css/web.xml etc files in this webapp subset folder.    		

7) This does not include Spring setup or anything beyond the basic additions.  See other readmes for details on subset issues.

10) See ...runMaven.. readme for details on server interaction- and specifically directed at tomcat.


   ---     
1) older notes for project creation: Open Java EE Perspective in Eclipse.  Java EE is intended for web apps amongst other Enterprise type 
	projects/functions.
	2.1) select/right click project, then Properties link. in window make sure there is a 'server' entry (or you cant launch it as a 
	web app	 this is why you selected the archetype in step 1.
	2.2) this particular archetype only lists src/main/resources under Java Resources.  typical java class file starts with
	src/main/java, as base then the Maven Group ID (com.prod in this example)
	 to instantiate this conventional package set (folders) you do the above steps

1) Click File-New-Other then Maven, new Maven project.  OR you can click new and Maven Project shows up on list, both produce same results.

1) Popup window- select:
	1) 1st pg-keep default base dir, and have been putting these in Java EE perspective, click 'simple/skip archetype' checkbox if needed, click next
	2) archetype-optional- 'org.codehaus.mojo.archetypes' 'webapp-javaee7' '1.1'.  there are many others to chose from.  
	or org.apache.maven.archetype / artifact id maven-archetype-j2ee-simple and version RELEASE.  this is under the Internal selection
	of the 2nd page 
	-  11/04/17- found w/ neural network web version that I had to skip the archetype and selected the simple/skip
	on the 1st pg.  otherwise system keep saying there was a duplicate project (??)  must be doing something wrong.
		will need to play around
	   with some of the spring ones to see what they do.  I have used a non default based on youtube video.  in Dec 16 was having issues w archetype library loading and eclipse was locking up.  got around this by using create simple project on 1st page. this created most of what was needed, just had to use existing projects as a template for the POM file.
	2) group id= 'com.prod' standard across projects. or 'com'  the string will be this group id plus artifact. ie com.prod.sessions under src.main.java.
		sort of arbitrary but seems to follow convention in books.  src/main/java is already part of javaee7 class path 
	3) artifact = 'sessions'  specific to project.  this is the name of the project that shows up in Project Explorer to left.
	4) hit finish button.
	--creates project--
	
5) Clear base project errors and folder mods
	1) Clear POM <executable> error.  Note once created I had to fix an issue with the POM- there is an <executions> block that has an error- either comment out or delete.  system will point you right to the offending line.  Deletion doesnt affect the ability to create or run the project later on, from what I have seen so far.
	2) Create a java Resources folder (if it doesnt already exist) for log files.  Right Click java folder, then new Source Folder, then type project name in 1st box then path in 2nd- starting with src.  ie src/main/resources and finish.
	3) Create WEB-INF folder. in src/main/webapp folder create a WEB-INF/web.xml folder and file.
	4) Create META-INF folder. in src/main/webapp folder create a META-INF dir [no files].  
	    -META-INF usually holds MANIFEST.MF file, but so far I have not had to create/update it manually.
	    -for some reason the ee7 version doesnt create these folders/files by default like the javaee1.4 version??  but once added it seems to pick them up 		and work without an issue.  Please note however if you copy the web.xml contents you need to check the contents.  Your new java dir structure will be 		different ie com.prod.sessions etc in servlet name tags specifically.
	5) Add POM.xml dependencies- for Customer support project (custSuptMaven) add new dependencies added by chapter.  In JWA book note that previous dependency 	tag groups are kept (except in rare cases) and new ones added to the end within <dependencies> tag block as needed.
	6) WEB-INF/web.xml- add appropriate deployment descriptors (if any).  As noted in JWA chapters.  See/copy spring-java-config web.xml for Spring projects.
	7) Add WEB-INF/jsp folder- goes under ...webapp/ folder.  will hold JWA .jsp files.
	8) Option 1 Classic- Add index.jsp and base.jspf files.  Index replaces basic index.html in src/main/webapp.  base.jspf goes under ..webapp/WEB_INF/jsp base dir (or per web.xml descriptor).  base holds the tag library allowing the jsp style c: designators to work (vs having to add the library to every .jsp file.  All commonly used 	functions should be held here.  Note tie to web.xml <jsp> tag set.
	9) Option 2 MVC- Add Spring structure if using Spring MVC.  see spring-java-config or springMvc project as a template.
		a- add java config package (dir) w. bootstrap/root/servlet classes.  there cannot be an index.jsp etc style file in root in this case.
		b- add java site package (dir) w. controller class(es) and repositories for database tables
	10) Establish log4j2.xml in java/resources folder for logging setup.  See springMvc or spring-java-config for examples.  alter .xml contents to reflect 	appropriate project name. Right click on Java folder and ..create new [need to add details]
	11) At this point you could put project under version control w/ git if needed. See PHP perspective/ Ajax project/readme git file for details.
		
	
6) ---details/supporting info and trouble shooting---   
   1) archetype note- use up to date version.  'webapp-javaee7' is current as of Jun 16.  Note that webapp-j2ee14 on video is a pretty old version- you need to stay current with the jdk you have loaded on your system.  so use the most up to date version.  in google search type org.codehaus.mojo.archetypes and use an up to date version.  as an example 1.4 doesnt support annotations in java. there are probably other archetype versions available via a little research online ie 'eclipse maven java 7 [or 8] web app archetype' or something similar.
   2) JavaSE vs Java EE- note that as of Jun16 Java SE (and JDK etc loaded in Eclipse) is ver 8.  However latest Java EE ver is 7.  Since you are creating a webapp you are using the EE ver.  See Java OTN for more details.
   -http://www.oracle.com/technetwork/java/index.html
   3) Spring MVC.  Spring Mvc archetypes are available- but need to play aroudn and do more research.
	
   3) project name (session) as artifact- to follow standard convention listed in Java Cookbook (JC), pg 20.  this maven project will establish 'src.main.java' by default and then your group id and artifact id will be tacked on to the end of that.
  a. See 'session' project.  and maven youtube video= https://www.youtube.com/watch?v=YeC7XQho-O0.  since you already added the codehaus ver using 'Add Archetype' function on 2nd pg its now in there by default.  you could add other ones this way later if needed.
  b. google search term = eclipse maven j2ee web project- this got me to the youtube video- there are more videos available also.
  c. DO NOT USE- 1) the apache webapp listed in the default is not a java style project and will not create a src java folder
     Or 2) the apache j2EE simple version.  Neither of these seem to create the project structure I anticipated, but the codehaus once did
  
   4) artifact id is  basic project name- keep all lower case and simple.  no spaces- its part of the path- and it is the thing that will show up in Project Explorer to left. then hit finish.  project will be created to left.

   5) Make sure you place the project in the base directory (default on first maven project page).  Otherwise use of a non-base folder will fail to create properly- it displays stuff out all over the place, and generates errors.  I think this is related to the default classpath constriant, but am not sure at this point- more research to do.

7) [pending] there is more research yet to do.

8) Perspective Notes:
1) Java EE Perspective -top right- is meant for web apps.
2) My Java perspective meant for POJO [plain old Java objects].  which may or may not be later incorporated into web apps via a .jar file.

9) Other Notes:
1) Basic Java Project creation.  For non web app, java file creation click on My Java Perspective in Eclipse and select Readme associated with Learning Java Book.

10) Maven Project tracking (those created in Eclipse workspace):
1) Jun16- sessions- chap 5 JWA book- http session/cookie examples
2) Jul16- custSuptMaven- JWA book ongoing 'customer-support' project.  created from scratch and changes as I read through chapters.  also import some of the downloaded versions 'customer-support-vXX' if I get stuck (not every code line/block is printed in book).

