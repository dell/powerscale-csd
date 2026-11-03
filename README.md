<!--
Copyright (c) 2021 Dell Inc., or its subsidiaries. All Rights Reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# PowerScale Custom Service Descriptor (CSD)

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](docs/CODE_OF_CONDUCT.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

Dell PowerScale Custom Service Descriptor (CSD) enables the use of Cloudera Manager
to provision OneFS as the storage service for a Cloudera Data Platform (CDP) Private
Cloud Base cluster.

## Table of Contents

* [Code of Conduct](./docs/CODE_OF_CONDUCT.md)
* [Maintainer Guide](./docs/MAINTAINERS.md)
* [Committer Guide](./docs/COMMITTER_GUIDE.md)
* [Contributing Guide](./docs/CONTRIBUTING.md)
* [Security](./docs/SECURITY.md)
* [Overview](#overview)
* [Building](#building)
* [Installation](#installation)
* [Configuration](#configuration)
* [Compatibility](#compatibility)
* [Support](#support)
* [License](#license)

## Overview

This CSD registers Dell PowerScale as a first-class storage service within Cloudera
Manager, allowing administrators to configure HDFS-compatible storage backed by a
PowerScale cluster.

Key features:

* Integrates PowerScale as an HDFS-compatible storage provider in Cloudera Manager
* Supports Kerberos authentication
* Configures HDFS client settings (short-circuit reads, token service IP handling)
* Gateway role for deploying Hadoop client configuration
* KMS service dependency for encryption support

## Building

The CSD is packaged as a JAR file. You can build it using the Cloudera Manager
Extensions validator and tooling:

```bash
# Clone the Cloudera Manager Extensions tools
git clone https://github.com/cloudera/cm_ext.git
cd cm_ext && mvn install

# Validate the CSD
java -jar validator/target/validator.jar -s descriptor/service.sdl

# Package as JAR
jar cf PowerScale-1.1.0.jar META-INF/ descriptor/ scripts/ images/
```

## Installation

1. Copy the CSD JAR to the Cloudera Manager CSD directory:
   ```bash
   cp PowerScale-1.1.0.jar /opt/cloudera/csd/
   chown cloudera-scm:cloudera-scm /opt/cloudera/csd/PowerScale-1.1.0.jar
   ```

2. Restart the Cloudera Manager Server:
   ```bash
   systemctl restart cloudera-scm-server
   ```

3. In Cloudera Manager, go to **Add Service** and select **Dell PowerScale**.

## Configuration

| Parameter | Description |
|-----------|-------------|
| Default File System URI | The full HDFS URI (e.g., `hdfs://powerscale.example.com:8020`) |
| WebHDFS URL | Full URL for the PowerScale WebHDFS interface |
| Kerberos Authentication | Enable if the cluster uses Kerberos |
| hadoop.security.token.service.use_ip | Controls whether tokens always use IP addresses (default: false) |
| Enable HDFS Short-Circuit Reads | Whether HDFS short-circuit reads are enabled (default: false) |

## Compatibility

| Component | Minimum Version |
|-----------|----------------|
| CDP Private Cloud Base | 7.1.7 |
| PowerScale OneFS | 8.2 |

## Support

The code and documentation are released with no warranties or SLAs and are
intended to be supported through a community driven process.

If you encounter any issues, please file an
[issue](https://github.com/dell/powerscale-csd/issues).

## License

This project is licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE)
for the full text, and [NOTICE](NOTICE) for attribution details.
