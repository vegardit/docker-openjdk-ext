# docker-openjdk-ext <a href="https://github.com/vegardit/docker-openjdk-ext/" title="GitHub Repo"><img height="30" src="https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/github.svg?sanitize=true"></a>

[![Build Status](https://github.com/vegardit/docker-openjdk-ext/workflows/Build/badge.svg "GitHub Actions")](https://github.com/vegardit/docker-openjdk-ext/actions?query=workflow%3ABuild)
[![License](https://img.shields.io/github/license/vegardit/docker-openjdk-ext.svg?label=license)](#license)
[![Docker Pulls](https://img.shields.io/docker/pulls/vegardit/openjdk-ext.svg)](https://hub.docker.com/r/vegardit/openjdk-ext)
[![Docker Stars](https://img.shields.io/docker/stars/vegardit/openjdk-ext.svg)](https://hub.docker.com/r/vegardit/openjdk-ext)
[![Docker Image Size](https://images.microbadger.com/badges/image/vegardit/openjdk-ext.svg)](https://hub.docker.com/r/vegardit/openjdk-ext)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)

1. [What is it?](#what-is-it)
1. [License](#license)


## <a name="what-is-it"></a>What is it?

This docker image extends the official [OpenJDK](https://hub.docker.com/_/openjdk) docker images by pre-installing git client, docker client, curl, less, and ps.

It is automatically built **daily** to include the latest OS security fixes.


## <a name="license"></a>License

All files in this repository are released under the [Apache License 2.0](LICENSE.txt).

Individual files contain the following tag instead of the full license text:
```
SPDX-License-Identifier: Apache-2.0
```

This enables machine processing of license information based on the SPDX License Identifiers that are available here: https://spdx.org/licenses/.
