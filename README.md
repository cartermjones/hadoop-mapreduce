# hadoop-mapreduce
This repository will be used to pool code and information pertaining to a project using Hadoop MapReduce in a Graduate Big Data course.

The instructions for the project are in Assignment2.pdf. The project uses Cloudera Hadoop running on VMWare. The Eclipse IDE included with the Cloudera Quickstart VM was used for development.

To run this as a JAR file in Cloudera, follow these steps:

1. Export the project as a JAR file (deselect 20-newsgroups from the export list) into the cloudera folder.

2. Make sure a copy of the 20-newsgroups dataset is on the Desktop. If you haven't made this copy, do so now.

3. Ensure that the HDFS and YARN services are running, and that the NameNode has left safe mode. 

4. In the terminal, run the following command to make a directory to house the input:

 <code> hdfs dfs -mkdir /user/cloudera/input/ </code>
 
5. Next, load the data from 20-newgroups into the input directory.

 <code>hdfs dfs -copyFromLocal ~/Desktop/20-newsgroups/ /user/cloudera/input/ </code>
 
 The terminal will probably complain the whole time (it will throw InterruptedException warnings, in my experience), but don't be alarmed! It's actually doing what it's supposed to be doing. Let it do its work. It may take a while.
 
 6. To run the JAR file, now enter the following in Terminal:
 
 <code> hadoop jar Assignment2.jar AssignmentDriver /user/cloudera/input/ /user/cloudera/output/ </code>
 
 If all goes well, this should properly produce the desired outputs. Check the results with the <code>hdfs dfs -ls</code> command. 



