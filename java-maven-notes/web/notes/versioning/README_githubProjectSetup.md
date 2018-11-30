Quick Reference- Git and Github register new project:
1) Create project in Eclipse
	1.1) See createMaven readme for details of project creation.
	1.2) Add some basic files so initial commits can be tested in both git [commit] and github [push].
	1.3) You must save all files prior to next step, or git creation will fail.  cant have any unsaved changes
	1.4) In Eclipse, select project, right click then Team/Share Project.
	1.5) in popups click git, then create a new git directory- see details below. 
		Use same project name for git folder name
	  	This physically moves the project from eclipse workspace folder to local git folder.
	  	In Eclipse it adds git decoration [name] and says ..NO-HEAD.  this is ok you havent committed any files yet
	1.6) In Eclipse right click project/team/commit
		make initial commits- do NOT push at this time.  Push is for web based github.  NO HEAD decoration changes to MASTER
	  	
2) Git- Create project in local git first
	2.1) Go into local version of Github (the github app icon on the desktop- this accesses local Git directory)
	2.2) Establish the project in there by selecting plus arrow icon in top left and click Add button [DO NOT create].
	2.3) use browse button to navigate to your git folder and select the project, click ok
	2.4) this makes your eclipse project visible in the local Github App.  Allow it a few seconds to update
		 it will refresh in the window.
	2.5) Click the Publish link.  this instantiates the project in GitHub
		Your Eclipse buttons for push are now visible- most were greyed out before.	
    
3) Test project
	3.1) In Eclipse you have already tested commit to local repo above
	3.2) Change a file, save.  Then Commit/Commit and Push to check both local and remote repo.
	3.3) after positive confirmation in Eclipse, go online and validate git hub update

Details:
1) Eclipse and Pycharm IDE are a little different in their relation to Ggit projects.  in Pycharm check suorganizer project 
README for details.  an excerpt from that
 ... To do this you DO NOT setup the project (repository) in GitHub first.  the desktop app does
    that for you.  Im my case I had to delete the online repository I created, but was empty.
    So unlike Eclipse/Java it doesnt actually move the project into its own git directory (and out of workspace).  Pycharm
    leaves the project in the directory as long as you have the right link to you local git dir.


2) Job/folder naming convention.  Note that the Java project name and the git folder name may or may not be the same. 
	Convention I have been using recently is to make a git subfolder with the same name 
	You would not typically put the project in the base git directory. (there is already custSuptMaven) setup that way
	If I had known at the time, I would have put it in a subfolder, like all the ones I did subsequently.
	If they are the same you will have 2 subsequent folders of the same name, but that is ok.  you can better manage multiple 
	projects by having them as subfolders under the main git folder.  as I have learned the hard way after initially 
	and mistekenly putting different project at the root git folder.
