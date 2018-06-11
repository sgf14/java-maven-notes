To run a non-web app type java program:

Quick Start:
Select My Java vs Java EE in header.  plain old java project are in that Perspective.
1) Main().  The file you wish to execute must have a main() method, or it has to have a call to a file w/ main().  
  In web apps the Server has this, and so you dont see it in any individual file.
2) Create/Save:  You have to save your changes.
3) Build Project: Right click on the project and 'Build Project'.  This compiles the .java to .class files (in the /bin folder usually)
4) Run As Java:  On the file, right click and select Run As/Java Application.
5) Results:  if you are outputting to console (System.out.println().  results should appear there.


Details:
1) Working Set Note:
  a.My Java- this is for POJO (plain old java object) type examples- vs Java Web apps.  Any typically for the working set under left hand side navigation- you will use the 2nd tab 'Navigator' [Working Set: Java Projects] vs Project Explorer [1st tab; working set, empty].  this will display JavaCompleteRefBook and this book,  LearningJava.  along with a few earlier java book examples
  
2) Setting up new java project.  
	File/New/Java Project.  follow wizard.
	Follow readme guidelines under SGF_Projects\LearningJava\  bases on lessons learned so far in setting these up in Eclipse so they are functional.