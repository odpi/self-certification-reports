# ODPi Compliance Process

## Table of Contents

* [1 ODPi Compliance Process](#odpi-compliance-process)
  * [1.1 Purpose of this document](#purpose-of-this-document)
    * [1.1.1 Definitions](#definitions)
  * [1.2 ODPi Compliance Program overview](#odpi-compliance-program-overview)
  * [1.3 Compliance Process](#compliance-process)
    * [1.3.1 ODPi Runtime Compliant](#odpi-runtime-compliant)
    * [1.3.2 ODPi Operations Compliant](#odpi-operations-compliant)
    * [1.3.3 ODPi Interoperable](#odpi-interoperable)
  * [1.4 Ongoing compliance](#ongoing-compliance)

## Purpose of this document

This document outlines the process needed for a product to fulfill the requirements for compliance with an ODPi Specification Release. ODPi Compliance is intended to be used by organizations to ensure their compliance with the big data industry standards governed by ODPi.

### Definitions

**Platform** - A product or service offering that consists of Apache Hadoop™, and optionally includes additional open source and/or commercial components that work with Apache Hadoop™.

**Platform Vendor**- An organization, either a commercial vendor or an open source project, that either produces a packaged version of the Platform or supports a service offering around the platform aimed at end-user consumption.

**Application** - A product that is intended to interoperate with a Platform.

**Software Vendor** - An organization, either a commercial vendor or an open source project, that has a product that works with a Platform.

**End Users** - Users of a Platform and/or Application.

**ODPi Runtime Specification** - Specification developed by the ODPi community that describes expected runtime behavior of a platform, located at [https://github.com/odpi/specs/blob/master/ODPi-Runtime.md](https://github.com/odpi/specs/blob/master/ODPi-Runtime.md).

**ODPi Runtime Test Harness** - Test harness developed by the [Apache Bigtop](https://bigtop.apache.org) community that verifies expected runtime behavior of an Apache Hadoop-based platform, available for download at [https://www.apache.org/dist/bigtop/1.2.0/bigtop-1.2.0-testsuite.zip](https://www.apache.org/dist/bigtop/1.2.0/bigtop-1.2.0-testsuite.zip).

**ODPi Operations Specification** - Specification developed by the ODPi community that describes expected operational behavior of an Apache Hadoop-based platform, located at [https://github.com/odpi/specs/blob/master/ODPi-Operations.md](https://github.com/odpi/specs/blob/master/ODPi-Operations.md).

**ODPi Specification Release** - A published version of the ODPi Runtime or ODPi Operations Specifications with an associated version number.

**ODPi Compliance Process** - The process defined by the ODPi TSC to validate and verify compliance with an ODPi Specification Release for an Platform Vendor or a Software Vendor.

## ODPi Compliance Program overview

The following matrix indicates the available programs, along with specification(s) and vendor classifications applicable for each.

<table>
  <tr>
    <td>Program</td>
    <td>Description</td>
    <td>Vendor type applicable for</td>
  </tr>
  <tr>
    <td>ODPi Runtime Compliant</td>
    <td>Confirms that a specific version of an Platform has been successfully tested against the ODPi Runtime Specification test harness.</td>
    <td>Platform Vendor</td>
  </tr>
  <tr>
    <td>ODPi Operations Compliant</td>
    <td>Confirms that a specific version of Platform is following ODPi Operations Specification guidelines. It also confirms that when a platform gets deployed using a bundled Hadoop Management Tool the result is ODPi Runtime compliant.</td>
    <td>Platform Vendor</td>
  </tr>
  <tr>
    <td>ODPi Interoperable</td>
    <td>Confirms that a specific version of an ISV Application leverages the components as outlined in a specific version of the ODPi Specification Release. </td>
    <td>Software Vendor</td>
  </tr>
</table>


## Compliance Process

There are specific steps required for each compliance program for the vendor to confirm compliance.

### ODPi Runtime Compliant

1. Review the most recently published [ODPi Runtime Spec](https://github.com/odpi/specs/blob/master/ODPi-Runtime.md).

2. Download the [latest Apache Bigtop acceptance test suite](https://www.apache.org/dist/bigtop/1.2.0/bigtop-1.2.0-testsuite.zip).

3. Unzip the test package on the primary machine on your Hadoop cluster you wish to test.

4. Install links on the primary machine on your Hadoop cluster you wish to test ( Either grab source from [http://links.twibright.com/download.php](http://links.twibright.com/download.php) or use the command below to install )
<pre>
sudo yum install links
</pre>

5. Run with user that has yarn admin privilages.

6. Make sure that user has passwordless sudo access and has a home directory e.g. /user/yarn in HDFS.

7. Use `./run_itest.sh -h` or `./run_itest.sh --help` to display arguments and defaults.
<pre>
Usage : ./run_itest.sh [-options]

   -j, --hivejdbc             hive jdbc url - default: e.g. jdbc:hive2://localhost:10000
   -m, --hivemeta             hive metastore url - default: thrift://localhost:9083
   -l, --hivelocation         location of hdfs for hive to write to - default: /tmp/<current user>
   -u, --hiveuser             hive user - default: hive
   -p, --hivepassword         hive user password - default: hive
   -t, --hivethrift           optional: true/false to test thrift, defaults to true
   -c, --hivecatalog          optional: true/false to test HCatalog, default to true
   -C, --hiveconf             hive conf dir - default: /etc/hive/conf
   -F, --hadoopconf           hadoop user - default: /etc/hadoop/conf
   -i, --info                 optional: info/debug
   -h, --help                 display this help and exit
</pre>

8. Run the tests, with needed arguments and optionally outputting the results to a text file.
<pre>
./run_itest.sh --info info > testresults.txt 2> testresults_verbose.txt
</pre>

9. If the test pass, issue a pull request with the text output in a file using the naming convention: <vendor name>/$HADOOP_VERSION-$OS-$ARCH-$SPECVERSION.txt to the [https://github.com/odpi/self-certification-reports](https://github.com/odpi/self-certification-reports) repository. If the test fails you will have to inspect testresults_verbose.txt and provide explanations for each failure.

10. A member of the ODPi TSC will review and merge in.

11. A member of the ODPi marketing team will follow up with trademark assets and guidelines for advertising ODPi compliance.

### ODPi Operations Compliant

1. Review the most recently published [ODPi Operations Spec](https://github.com/odpi/specs/blob/master/ODPi-Operations.md).

2. Deploy a platform using a bundled Hadoop Management Tool.

3. Verify that the resulting platform confirms to the ODPi Runtime specification as per previous section.

4. Capture environment information using script available under http://XXXX 

5. Issue a pull request with the text output of steps #3 and #4 in a file using the naming convention: <vendor name>/$HADOOP_VERSION-$OS-$ARCH-$SPECVERSION.txt to the [https://github.com/odpi/self-certification-reports](https://github.com/odpi/self-certification-reports) repository.

6. A member of the ODPi TSC will review and merge in.

7. A member of the ODPi marketing team will follow up with trademark assets and guidelines for advertising ODPi compliance.

### ODPi Interoperable

1. Review the most recently published [ODPi Runtime Spec](https://github.com/odpi/specs/blob/master/ODPi-Runtime.md) and [ODPi Operations Spec](https://github.com/odpi/specs/blob/master/ODPi-Operations.md).

2. Install (or gain access to) a Platform that is compliant with the latest version of the ODPi Specification Release. While it is not strictly required, we highly recommend that you also consider installing an ODPi reference implementation platform in addition to a vendor’s one. Running the tests on ODPi reference implementation guarantees that only ODPi core component get deployed and also helps with having an access to a 100% open platform, unencumbered with EULAs.

3. Complete the questionnaire outlined below ( all info to be shared publically )

    1. Product name / version

    2. Primary contact for questions on this questionnaire

    3. Which technologies governed by the ODPi Runtime Specification does this application interoperate with?

    4. Which ODPi-compliant distributions and versions did you test with?

    5. Did you deploy, configure and operated your application using ODPi Operations compatible Hadoop Management Tool?

    6. If your application supports a deployment and configuration model other than using and ODPi Operations compatible Hadoop Management Tool please describe it here.

    7. Please describe your testing procedure you use to demonstrate compatibility and what passing results will be.

    8. What modifications did you make to your software or underlying configurations for each distribution in order for them to pass?

    9. Did you test with any ODPi-compliant distributions that did not pass your interoperability tests?

   10. Did you notice any different behavior in your software or the underlying distributions when you ran your tests, whether or not you deemed the tests as passing?

   11. Which ODPi-compliant distributions and versions do you provide support for in the deployment of your software?

4. Issue a pull request with the text output in a file using the naming convention: <vendor name>/$PRODUCT_NAME_AND_VERSION-$SPECVERSION.txt to the [https://github.com/odpi/self-certification-reports](https://github.com/odpi/self-certification-reports) repository.

5. A member of the ODPi TSC will review and merge in.

6. A member of the ODPi marketing team will follow up with trademark assets and guidelines for advertising ODPi compliance.

## Ongoing compliance

ODPi compliance is not a one time event, but an ongoing commitment between Platform Vendors, ISVs, and the ODPi to ensure that the best practices outlined by the ODPi Specification Releases are adhered to for the benefit of End Users. As such, ODPi has the following requirements and recommendations for ongoing compliance.

* Platform Vendors and Software Vendors should look to include the ODPi Compliance Process as a part of their integration testing and release process.

* Platform Vendors and Software Vendors are required to submit a new report for each ODPi Specification Release subsequent to the first ODPi Specification Release they complete the ODPi Compliance Process for. 

* ODPi will publish the results of ODPi compliance testing to the ODPi website.

