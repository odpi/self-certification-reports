* Product name / version

Data Ingestion Platform (DiP)

* Primary contact for questions on this questionnaire 

Neeraj Sabharwal 

* Which technologies governed by the ODPi Runtime Specification does this application interoperate with?

Hortonworks Data Platform (HDP) , latest version that we have tested is HDP 2.4.2 and HDP 2.5 is work in progress.

* Which ODPi-compliant distributions and versions did you test with?

odpi-1.0

* Please describe your application deployment and configuration process (if any). If the application lends itself to be managed by a tool compatible with ODPi Operations specification please make sure to use the appropriate tool.

Users can dowload the application from github and deploy it in their cluster. https://github.com/XavientInformationSystems/Data-Ingestion-Platform

* Please describe your testing procedure you use to demonstrate compatibility and what passing results will be.

Hortonworks Data Platform was installed with Hadoop and other components from Hadoop ecosystem like Hive, Hbase, Storm, Flink and Apex. Data loading was done using Kafka into Lambda architecture. 

* What modifications did you make to your software or underlying configurations for each distribution in order for them to pass?
We did not make any major changes except few changes in our configs to resolve dependencies issues unrelated to odpi.

* Did you test with any ODPi-compliant distributions that did not pass your interoperability tests?

No

* Did you notice any different behavior in your software or the underlying distributions when you ran your tests, whether or not you deemed the tests as passing?

No

* Which ODPi-compliant distributions and versions do you provide support for in the deployment of your software?
odpi-1.0
