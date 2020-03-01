# Become an Elastic Certified Engineer


## Contents

1. [Lab environments](#lab-environment)
   * [Linux VM](#linux-vm)
   * [Docker for Desktop](#docker-for-desktop)
     * [Windows](#windows)
     * [Linux](#linux)
     * [macOS](#macos)
2. [Useful URL](#useful-url)


## Lab environment

### Linux VM

You can install ELK on your Linux server

### Docker for Desktop

* [Docker Engine](https://docs.docker.com/install/) version **17.05+**
* [Docker Compose](https://docs.docker.com/compose/install/) version **1.12.0+**
* 1.5 GB of RAM
By default, the stack exposes the following ports:
* 9200: Elasticsearch HTTP
* 9300: Elasticsearch TCP transport
* 5601: Kibana

#### Windows

Ensure the [Shared Drives][win-shareddrives] feature is enabled for the `C:` drive.

#### Linux

Install Docker on Linux

#### macOS

The default Docker for Mac configuration allows mounting files from `/Users/`, `/Volumes/`, `/private/`, and `/tmp`
exclusively. Make sure the repository is cloned in one of those locations or follow the instructions from the
[documentation][mac-mounts] to add more locations.


## Useful URL

Official URL
* [Register Elastic Certified Engineer](https://training.elastic.co/exam/elastic-certified-engineer)
* [`FAQ`](https://www.elastic.co/training/certification/faq): Certification FAQ 



[elk-stack]: https://www.elastic.co/elk-stack
[stack-features]: https://www.elastic.co/products/stack

[config-es]: ./elasticsearch/config/elasticsearch.yml
[config-kbn]: ./kibana/config/kibana.yml
[config-ls]: ./logstash/config/logstash.yml
