There are several types of logging from basic console to advanced APIs.  This file focuses on log4j.
System.out.print()

Quick start:
1) Once project is setup add pom.xml dependencies, there are typically 5- see chap 11 note below
2) Add src/main/resources/log4j2.xml file with basic setup.  See custSuptMaven project for example.
3) Add a log.info() stmt to one class file for testing
4) clean/install maven.  run on server.  Test log file and console [default xml file setup logs to both].

Details:
1) this is largely based on Java For Web Applications - chapter 11 examples- pg 297.  confirmed steps 1-4 worked in j2ee-design project.
2) there is also java.util.logging classes also.  See example in j2ee-design & and noted in book.  so far I have only got
that setup to report in console, but there may be similar xml file setup to create a log file itself.  Apache's log4j works well
enough, so havent invested the effort on java.util, slf4 etc, which offer other logging API's.
