Product: Integration tests for WSO2 ESB acquia connector

Pre-requisites:

 - Maven 3.x
 - Java 1.6 or above

Tested Platform:

 - Ubuntu 14.04 64bit
 - WSO2 ESB 4.8.1
 - Java 1.6 or above


1.ESB Axis2 configurations

Ensure that the following Axis2 configurations are added and enabled in the <ESB_HOME>\repository\conf\axis2\axis2.xml file.

    messageFormatters
        <messageFormatter contentType="text/html" class="org.wso2.carbon.relay.ExpandingMessageFormatter"/>

    messageBuilders
        <messageBuilder contentType="text/html" class="org.wso2.carbon.relay.BinaryRelayBuilder"/>

Running the integration test

STEPS:

1.Download ESB 4.8.1 from the official website.

2.Get the access credentials for Lift Web Key and S3 Bucket.

3.Compress the modified ESB as wso2esb-4.8.1.zip and copy that zip file to the location acquia/acquia-connector/acquia-connector-1.0.0/org.wso2.carbon.connector.acquia.contextdb/repository/.

4.Update the property file AcquiaContextDb.properties found in acquia/acquia-connector/acquia-connector-1.0.0/org.wso2.carbon.connector/src/test/resources/artifacts/ESB/connector/config as given below:

    proxyDirectoryRelativePath=/../src/test/resources/artifacts/ESB/config/proxies/AcquiaContextDb/
    requestDirectoryRelativePath=/../src/test/resources/artifacts/ESB/config/restRequests/AcquiaContextDb/
    secretKey=WiCMOM3brsjgDFKvGqphrWB9Etn4lszgIbZp6GiE
    accessKey=AvqEKDHSP3OoeOWwdNT2
    accountId=WS02SANDBOX
    eventName=xx
    type=Other
    startDate=2014-12-01
    dataExport=person
    statusId=50
    identifier=elil
    identifierType=name
    personTables=person
    identity=10244
    identitySource=name
    eventName=Campaign Action
    eventSource=TruCentric

5.Navigate to acquia/acquia-connector/acquia-connector-1.0.0/org.wso2.carbon.connector.acquia.contextdb/ and run the following command.
  $ mvn clean install
