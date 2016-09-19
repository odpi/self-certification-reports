# Pivotal HDB Self Certification for ODPi Interoperability

**I. Product name / version**  
Pivotal HDB 2.0 Powered by Apache HAWQ

**II. Primary contact for questions on this questionnaire**  
Vineet Goel  
vgoel@pivotal.io  

**III. Which technologies governed by the ODPi Runtime Specification does this application interoperate with?***  
Hadoop Common, HDFS, YARN  

**IV. Which ODPi-compliant distributions and versions did you test with?**  
ODPi Reference, Hortonworks HDP 2.4.2  

**V. Please describe your application deployment and configuration process (if any). If the application lends itself to be managed by a tool compatible with ODPi Operations specification please make sure to use the appropriate tool.**  
Pivotal HDB and Apache HAWQ can be installed and configured through a manual process, as well as via Apache Ambari.  For purposes of interoperability testing, we installed Pivotal HDB through a manual process.

**VI. Please describe your testing procedure you use to demonstrate compatibility and what passing results will be.**  
Here is an overview of the testing procedure we ran to test Pivotal HDB with the ODPi Reference Implementation of Hadoop as well as one of the first ODPi Runtime Compliant distributions, Hortonworks HDP v. 2.4.2   

We tested the same version of Pivotal HDB software using the same configuration settings against both platforms. The installation was successful in both cases, and the tests finished identically.  
1. Install ODPi-compliant Hadoop Distribution onto cluster. Expected result:Hadoop cluster alive and functioning normally.  
2. Install Pivotal HDB. Expected result: the installation process completes without errors.  
3. Smoke test with 1GB of data. Expected result: load 1 GB of data and run simple short queries and see that behavior operates as expected.  
4. 3TB TPC-DS-derived benchmark test with the HDB default resource manager Expected result: execute long running  benchmark based on TPC-DS with a 3TB data set and observe the expected behavior and performance.  
5. 3TB TPC-DS-derived benchmark test with HDB configured to utilize YARN as resource manager. Expected result: xecute long running benchmark based on TPC-DS with a 3TB data set with YARN resource management configured and observe the expected behavior and performance.    

We designed a benchmark test based on the 99 standard TPC-DS queries and executed the benchmark using 3TB of data on 10 AWS nodes.  Each node had 64GB of RAM and only 1 large disk. The NameNode, YARN Resource Manager, and the HDB Master were co-located on DataNodes instead of having dedicated nodes.  Both Resource Managers (YARN and the default) were tested successfully.  

Pivotal HDB executed all 99 queries of the benchmark test without issue. The execution time was also consistent with the performance we’ve seen at the other times we’ve run this  benchmark test.

**VII. What modifications did you make to your software or underlying configurations for each distribution in order for them to pass?**  
	None  
	
**VIII. Did you test with any ODPi-compliant distributions that did not pass your interoperability tests?**  
	No additional distributions tested.  
	
**IX. Did you notice any different behavior in your software or the underlying distributions when you ran your tests, whether or not you deemed the tests as passing?**  
	No difference.
	
**X. Which ODPi-compliant distributions and versions do you provide support for in the deployment of your software?**  
	Hortonworks HDP 2.4.2
