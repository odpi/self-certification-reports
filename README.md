# ODPi self-certification reports

This repository consists of the ODPi compliance and ODPi interoperability results submitted by ODPi member companies. 
Submitting a pull request to this repository or sending an email to odpi-interoperable@odpi.org is the first step
in the process of acquiring ODPi Compliant and/or ODPi interoperable designation.

## How to submit self certification

### ODPi Runtime Compliant

1. Download the latest acceptance test suite ( Current is at http://repo.odpi.org/ODPi/1.0/acceptance-tests/ ).
2. Unzip the test package on the primary machine on your Hadoop cluster you wish to test.
3. Install links on the primary machine on your Hadoop cluster you wish to test ( Either grab source from http://links.twibright.com/download.php or use the command below to install )

    ```
    sudo yum install links
    ```

4. Run the tests, optionally outputing the results to a text file

    ```
    ./run_itest.sh > testresults.txt
    ```

4. If the test pass, issue a pull request with the text output in a file using the naming convention: $HADOOP_VERSION-$OS-$ARCH-$SPECVERSION.xml to this repository under a directory named for your company/organizational name.
5. A member of the ODPi will review and merge in.
6. A member of the ODPi marketing team will follow up with trademark assets and guidelines for advertising ODPi compliance.

### ODPi Operations Compliant

1. Download the latest acceptance test suite ( Current is at http://repo.odpi.org/ODPi/1.0/acceptance-tests/ ).
2. Unzip the test package on the primary machine on your Hadoop cluster you wish to test.
3. Install links on the primary machine on your Hadoop cluster you wish to test ( Either grab source from http://links.twibright.com/download.php or use the command below to install )

    ```
    sudo yum install links
    ```

4. Run the tests, optionally outputing the results to a text file

    ```
    ./run_itest.sh > testresults.txt
    ```

4. If the test pass, issue a pull request with the text output in a file using the naming convention: $HADOOP_VERSION-$OS-$ARCH-$SPECVERSION.xml to this repository under a directory named for your company/organizational name.
5. A member of the ODPi will review and merge in.
6. A member of the ODPi marketing team will follow up with trademark assets and guidelines for advertising ODPi compliance.

### ODPi Interoperable

1. Review the most recently published ODPi Runtime Spec and ODPi Operations Spec.
2. Install (or gain access to) an Apache Hadoop-based Platform Distribution that is compliant with the latest version of the ODPi Specification Release. While it is not strictly required, we highly recommend that you also consider installing an ODPi reference implementation platform in addition to a vendor’s one. Running the tests on ODPi reference implementation guarantees that only ODPi core component get deployed and also helps with having an access to a 100% open platform, unencumbered with EULAs.
3. Complete the questionnaire outlined below ( all info to be shared publically )
   * Product name / version
   * Primary contact for questions on this questionnaire
   * Which technologies governed by the ODPi Runtime Specification does this application interoperate with?
   * Which ODPi-compliant distributions and versions did you test with?
   * Please describe your application deployment and configuration process (if any). If the application lends itself to be managed by a tool compatible with ODPi Operations specification please make sure to use the appropriate tool.
   * Please describe your testing procedure you use to demonstrate compatibility of an Apache Hadoop Distribution, and what passing results will be.
   * What modifications did you make to your software or underlying configurations for each distribution in order for them to pass?
   * Did you test with any ODPi-compliant distributions that did not pass your interoperability tests?
   * Did you notice any different behavior in your software or the underlying distributions when you ran your tests, whether or not you deemed the tests as passing?
   * Which ODPi-compliant distributions and versions do you provide support for in the deployment of your software?
4. Submit this questionnaire to odpi-interoperable@odpi.org or issue a pull request to this repository
5. A member of the ODPi TSC will review and follow up with approval.
6. A member of the ODPi marketing team will follow up with trademark assets and guidelines for advertising ODPi compliance.
