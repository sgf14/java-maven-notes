in AWS creating a java project:
[ OLD-OLD- need to load aws word doc to here- or retrofit this]
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

Notes:
jdk8 download- this worked 05/20/18
wget -c --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.rpm
**OLD**
java8 download: in google type install java linux wget (as of may 18- this changes over time) glassfish 4.1.2 needs jdk1.8
web result:
https://gist.github.com/hgomez/9650687
cmd- linux wget
wget --continue --no-check-certificate -O jdk-8-linux-x64.tar.gz --header Cookie: oraclelicense=a http://download.oracle.com/otn-pub/java/jdk/8-b132/jdk-8-linux-x64.tar.gz
