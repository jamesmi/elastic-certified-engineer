# Become an Elastic Certified Engineer


## Contents

1. [Lab environments](#lab-environment)
   * [Linux VM](#linux-vm)
   * [Docker for Desktop](#docker-for-desktop)
     * [macOS](#macos)
     * [Linux](#linux)
2. [Useful URL](#useful-url)



## Lab environment

### Linux VM

You can install ELK on your Linux server

### Docker for Desktop

* [Docker Engine](https://docs.docker.com/install/) version **17.05+**
* [Docker Compose](https://docs.docker.com/compose/install/) version **1.12.0+**
* Resources: CPUs 2, Memory 4GB, Disk 40GB

In our lab environments, the elastic stack exposes the following ports:

single-node-cluster
* 19200: Elasticsearch HTTP
* 19300: Elasticsearch TCP transport
* 15601: Kibana

three-nodes-cluster
* 9200: Elasticsearch HTTP
* 9300: Elasticsearch TCP transport
* 5601: Kibana


#### macOS
Install [Docker for Mac](https://docs.docker.com/docker-for-mac/install/)

The default Docker for Mac configuration allows mounting files from `/Users/`, `/Volumes/`, `/private/`, and `/tmp`
exclusively.

* [Download Docker Images](https://www.docker.elastic.co/) version **7.2.1**
```console
James-MacBook:~ james$ docker pull docker.elastic.co/elasticsearch/elasticsearch:7.2.1
James-MacBook:~ james$ docker pull docker.elastic.co/kibana/kibana:7.2.1
James-MacBook:~ james$ docker pull docker.elastic.co/logstash/logstash:7.2.1
James-MacBook:~ james$ docker pull docker.elastic.co/beats/filebeat:7.2.1
James-MacBook:~ james$ docker image ls
REPOSITORY                                      TAG                 IMAGE ID            CREATED             SIZE
docker.elastic.co/logstash/logstash             7.2.1               398ae1bce45b        7 months ago        837MB
docker.elastic.co/kibana/kibana                 7.2.1               a9d9159c1e37        7 months ago        891MB
docker.elastic.co/elasticsearch/elasticsearch   7.2.1               1e8add8d7b66        7 months ago        862MB
docker.elastic.co/beats/filebeat                7.2.1               7bd56506b1d7        7 months ago        362MB
James-MacBook:elastic-docker james$
```


#### Linux

Install Docker on Linux


## Useful URL

Official URL
* [Register Elastic Certified Engineer](https://training.elastic.co/exam/elastic-certified-engineer)
* [Run the Elastic Stack on Docker](https://www.elastic.co/guide/en/elastic-stack-get-started/master/get-started-docker.html)
* [Docker Compose Command](https://docs.docker.com/compose/reference/overview/)
* [Elasticsearch on docker](https://www.elastic.co/guide/en/elasticsearch/reference/7.2/docker.html)
* [The definitive guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/index.html)
* [Elasticsearch reference](https://www.elastic.co/guide/en/elasticsearch/reference/7.2/index.html)
* [`FAQ`](https://www.elastic.co/training/certification/faq): Certification FAQ 






[elk-stack]: https://www.elastic.co/elk-stack
[stack-features]: https://www.elastic.co/products/stack

[config-es]: ./elasticsearch/config/elasticsearch.yml
[config-kbn]: ./kibana/config/kibana.yml
[config-ls]: ./logstash/config/logstash.yml
