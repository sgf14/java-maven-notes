in AWS creating a java project:

quickstart- Glassfish server
1) Elastic bean stalk- 
  1-1) keep the sample project first.  pick Docker/glassfish.  do simple launch initially, then upload your project later
  1-2) in security section- add a SSH key pair you created.  note each region has its own key pair
  1-3) create a db connection. 
  1-4) launch project
2) RDS- create/make sure DB instance is running
3) SSH CLI- configure Glassfish server for db
  3-1) can only do this in CLI.  unlike localhost:4848\ there is no admin console avail. so launch putty/connect. see notepad++ aws file
  3-2) working on this
4) Ec2- once sample project link tested ok, upload your maven .war file and hit deploy.

quickstart- Tomcat server
[pending]

quickstart- Mysql db and cnx to my local SQL editor
1) Create RDS- new mysql entry
2) see j2eeAlt project already connected as sample.  up and working in mySql editor
3) use EC2 as host 
		enter key-pair for ssh
		and db endpoint as xx. 
		enter username and db password you setup in AWS 
		see youtube video.  make a screenshot of this for ref.
4) click open to make sure it connects