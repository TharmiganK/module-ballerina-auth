Ballerina Auth Library
===================

  [![Build](https://github.com/ballerina-platform/module-ballerina-auth/actions/workflows/build-timestamped-master.yml/badge.svg)](https://github.com/ballerina-platform/module-ballerina-auth/actions/workflows/build-timestamped-master.yml)
  [![Trivy](https://github.com/ballerina-platform/module-ballerina-auth/actions/workflows/trivy-scan.yml/badge.svg)](https://github.com/ballerina-platform/module-ballerina-auth/actions/workflows/trivy-scan.yml)  
  [![GitHub Last Commit](https://img.shields.io/github/last-commit/ballerina-platform/module-ballerina-auth.svg?label=Last%20Commit)](https://github.com/ballerina-platform/module-ballerina-auth/commits/master)
  [![GitHub issues](https://img.shields.io/github/issues/ballerina-platform/ballerina-standard-library/module/auth.svg?label=Open%20Issues)](https://github.com/ballerina-platform/ballerina-standard-library/labels/module%2Fauth)
  [![codecov](https://codecov.io/gh/ballerina-platform/module-ballerina-auth/branch/master/graph/badge.svg)](https://codecov.io/gh/ballerina-platform/module-ballerina-auth) 

This module provides a framework for authentication/authorization based on the Basic Authentication scheme specified in [RFC 7617](https://datatracker.ietf.org/doc/html/rfc7617).

The Basic Authentication scheme transmits credentials as user-id/password pairs encoded using Base64. This scheme is not considered to be a secure method of user authentication unless used in conjunction with some external secure system such as TLS as the user ID and password are passed over the network as cleartext.

The Ballerina `auth` module facilitates auth providers that are to be used by the clients and listeners of different protocol connectors.

### Listener File User Store Basic Auth Provider

Represents the file user store based listener Basic Auth provider, which is used to authenticate the provided credentials against the provided file user store configurations. The users are denoted by a section in the `Config.toml` file. The username, password, and the scopes of a particular user are denoted as keys under the `users` section as shown below. For multiple users, the complete section has to be duplicated.

```toml
[[ballerina.auth.users]]
username="alice"
password="xxx"
scopes=["read", "write"]
```

### Listener LDAP User Store Basic Auth Provider

Represents the LDAP-based listener Basic Auth provider, which is used to authenticate the provided credentials against the provided LDAP user store configurations. This connects to an active directory or an LDAP, which retrieves the necessary user information and performs authentication and authorization.

### Client Basic Auth Provider

Represents the client Basic Auth provider, which is used to authenticate with an external endpoint by generating a Basic Auth token against the provided credential configurations.

## Issues and Projects

Issues and Projects tabs are disabled for this repository as this is part of the Ballerina Standard Library. To report bugs, request new features, start new discussions, view project boards, etc., go to the [Ballerina Standard Library parent repository](https://github.com/ballerina-platform/ballerina-standard-library).

This repository only contains the source code for the module.

## Building from the Source

### Setting Up the Prerequisites

1. Download and install Java SE Development Kit (JDK) version 11 (from one of the following locations).

   * [Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
   
   * [OpenJDK](https://adoptopenjdk.net)
   
        > **Note:** Set the `JAVA_HOME` environment variable to the path name of the directory into which you installed JDK.

2. Export your GitHub Personal Access Token (PAT) with the `read package` permission as follows:

    ```
    export packageUser=<Username>
    export packagePAT=<Personal Access Token>
    ```

3. Download and install [Docker](https://www.docker.com/).

### Building the Source

Execute the commands below to build from the source.

1. To build the package:
    ```    
    ./gradlew clean build
    ```
2. To run the tests:
    ```
    ./gradlew clean test
    ```

3. To run a group of tests
    ```
    ./gradlew clean test -Pgroups=<test_group_names>
    ```

4. To build the without the tests:
    ```
    ./gradlew clean build -x test
    ```

5. To debug package implementation:
    ```
    ./gradlew clean build -Pdebug=<port>
    ```

6. To debug with Ballerina language:
    ```
    ./gradlew clean build -PbalJavaDebug=<port>
    ```

7. Publish the generated artifacts to the local Ballerina central repository:
    ```
    ./gradlew clean build -PpublishToLocalCentral=true
    ```

8. Publish the generated artifacts to the Ballerina central repository:
    ```
    ./gradlew clean build -PpublishToCentral=true
    ```

## Contributing to Ballerina

As an open source project, Ballerina welcomes contributions from the community.

For more information, go to the [contribution guidelines](https://github.com/ballerina-platform/ballerina-lang/blob/master/CONTRIBUTING.md).

## Code of Conduct

All contributors are encouraged to read the [Ballerina Code of Conduct](https://ballerina.io/code-of-conduct).

## Useful Links

* Chat live with us via our [Slack channel](https://ballerina.io/community/slack/).
* Post all technical questions on Stack Overflow with the [#ballerina](https://stackoverflow.com/questions/tagged/ballerina) tag.
