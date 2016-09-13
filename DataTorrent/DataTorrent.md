# DataTorrent ODPi Interoperable Certification

## a. Product name / version 
DataTottent Real Time Streaming

## b. Primary contact for questions on this questionnaire 
Pritesh Maker (pritesh@datatorrent.com)

## c. Which technologies governed by the ODPi Runtime Specification does this application interoperate with? 
Hadoop common, HDFS, Yarn

## d. Which ODPi­compliant distributions and versions did you test with? 
ODPi Reference, Hortonworks HDP 2.4.2

## e. Please describe your application deployment and configuration process (if any). If the application lends itself to be managed by a tool compatible with ODPi Operations specification please make sure to use the appropriate tool. 

Download and run the installer binary on one of the Hadoop cluster nodes. This can be done on ResourceManager, NameNode, or any node which has correct Hadoop configuration and is able to communicate with the rest of the cluster.
    curl -LSO https://www.datatorrent.com/downloads/datatorrent-rts.bin
    sh ./datatorrent-rts.bin

Add DataTorrent binaries to user PATH environment variable by pasting following into ~/.bashrc, ~/.profile or equivalent environment settings file.

    DATATORRENT_HOME=~/datatorrent/current
    export PATH=$PATH:$DATATORRENT_HOME/bin

## f. Please describe your testing procedure you use to demonstrate compatibility and  what passing results will be. 
Our Testing involves, installing DataTorrenr RTS on hadoop distribution & launch the application for processing data in streaming fashion & ran the ODPi acceptance suite 

## g. What modifications did you make to your software or underlying configurations for each distribution in order for them to pass? 
NA

## h. Did you test with any ODPi­compliant distributions that did not pass your interoperability tests? 
No

## i. Did you notice any different behavior in your software or the underlying distributions when you ran your tests, whether or not you deemed the tests as passing? 
No

## j. Which ODPi­compliant distributions and versions do you provide support for in the deployment of your software?
Hortonworks HDP 2.4.2
