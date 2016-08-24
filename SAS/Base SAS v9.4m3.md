# SAS ODPi Interoperable Certification

## a. Product name / version
Base SAS v9.4m3
SAS/Access Interface to Hadoop

## b. Primary contact for questions on this questionnaire
Clint Edwards (clint dot edwards at sas.com)

## c. Which technologies governed by the ODPi Runtime Specification does this application interoperate with?
Hadoop common, HDFS, Mapreduce

## d. Which ODPi compliant distributions and versions did you test with?
ODPi Reference, Hortonworks HDP 2.4.2

## e. Please describe your testing procedure you use to demonstrate compatibility of a Hadoop distribution, and what passing results will be.
The testing involved a single machine with Base SAS and SAS/Access interface to Hadoop installed, along with a single node hadoop cluster with either the ODPi reference platform or Hortonworks HDP 2.4.2 installed. Our tests exercised various API calls to HDFS, and Mapreduce. The tests were deemed passing because the results were the same as previous versions of Hortonworks HDP.


## f. What modifications did you make to your software or underlying configurations for each distribution in order for them to pass?
We did not make any modifications to our software and we did not make any underlying configuration changes.

## g. Did you test with any ODPi compliant distributions that did not pass your interoperability tests?
No.

## h. Did you notice any different behavior in your software or the underlying distributions when you ran your tests, whether or not you deemed the tests as passing?
No.

## i. Which ODPi compliant distributions and versions do you provide support for in the deployment of your software?
Hortonworks HDP 2.4.2
IBM BigInsights 4.2

