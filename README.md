# Become an Elastic Certified Engineer


## Contents

1. [Lab environments](#lab-environment)
   * [Linux VM](#linux-vm)
   * [Docker for Desktop](#docker-for-desktop)
     * [macOS](#macos)
     * [Linux](#linux)
2. [Reference](#reference)
   * [Elastic Stack](#elastic-stack)
   * [Docker](#docker)
   

## Lab environment

Elastic Stack docker detail information

| Cluster             | Detail               |
|---------------------|----------------------|
| single-node-cluster | 1 ES, 1 Kibana       |
| three-nodes-cluster | 3 ES, 1 Kibana       |
    
In our lab environments, the elastic stack exposes the following ports:

  single-node-cluster
  * 19200: Elasticsearch HTTP
  * 19300: Elasticsearch TCP transport
  * 15601: Kibana

  three-nodes-cluster
  * 9200: Elasticsearch HTTP
  * 9300: Elasticsearch TCP transport
  * 5601: Kibana
  
### Linux VM

You can install ELK on your Linux server

### Docker for Desktop

* [Docker Engine](https://docs.docker.com/install/) version **17.05+**
* [Docker Compose](https://docs.docker.com/compose/install/) version **1.12.0+**
* Resources: CPUs 2, Memory 4GB, Disk 40GB
 

#### macOS

The default Docker for Mac configuration allows mounting files from `/Users/`, `/Volumes/`, `/private/`, and `/tmp`
exclusively.

* Install [Docker for Mac](https://docs.docker.com/docker-for-mac/install/)

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

* Start single-node-cluster via docker-compose command
  ```console
  James-MacBook:elastic-docker james$ cd single-node-cluster/
  James-MacBook:single-node-cluster james$ ls
  docker-compose.yml
  James-MacBook:single-node-cluster james$ docker-compose up
  ```

* Check Elasticsearch and Kibana status

    Kibana: http://localhost:15601/status
    
    APIs:
    ```console
    James-MacBook:~ james$ curl http://localhost:19200/_cat/nodes
    172.22.0.2 39 97 6 0.67 0.52 0.56 mdi * elasticsearch01
    James-MacBook:~ james$ curl http://localhost:15601/api/status
    ```

* Start three-nodes-cluster via docker-compose command
  ```console
  James-MacBook:elastic-docker james$ cd three-nodes-cluster/
  James-MacBook:three-nodes-cluster james$ ls
  docker-compose.yml
  James-MacBook:single-node-cluster james$ docker-compose up
  ```
* Check container status
  ```console
  James-MacBook:three-nodes-cluster james$ docker-compose ps
  Name              Command               State                Ports              
  --------------------------------------------------------------------------------
  es01   /usr/local/bin/docker-entr ...   Up      0.0.0.0:9200->9200/tcp, 9300/tcp
  es02   /usr/local/bin/docker-entr ...   Up      0.0.0.0:9201->9200/tcp, 9300/tcp
  es03   /usr/local/bin/docker-entr ...   Up      0.0.0.0:9202->9200/tcp, 9300/tcp
  kb01   /usr/local/bin/kibana-docker     Up      0.0.0.0:5601->5601/tcp          
  James-MacBook:three-nodes-cluster james$
  ```

* Check Elasticsearch and Kibana status

    Kibana: http://localhost:5601/status
    
    APIs:
    ```console
    James-MacBook:~ james$ curl -u elastic:changeme http://localhost:9200/_cat/nodes
    172.24.0.3 40 97 15 0.42 0.41 0.44 mdi * es03
    172.24.0.2 47 97 16 0.42 0.41 0.44 mdi - es02
    172.24.0.4 33 97 10 0.42 0.41 0.44 mdi - es01
    James-MacBook:~ james$ curl -u elastic:changeme http://localhost:9200
    {
      "name" : "es01",
      "cluster_name" : "docker-cluster",
      "cluster_uuid" : "BWeXUEp4RMCIK_TKcEfSuw",
      "version" : {
        "number" : "7.2.1",
        "build_flavor" : "default",
        "build_type" : "docker",
        "build_hash" : "fe6cb20",
        "build_date" : "2019-07-24T17:58:29.979462Z",
        "build_snapshot" : false,
        "lucene_version" : "8.0.0",
        "minimum_wire_compatibility_version" : "6.8.0",
        "minimum_index_compatibility_version" : "6.0.0-beta1"
      },
      "tagline" : "You Know, for Search"
    }
    James-MacBook:~ james$ 
    James-MacBook:~ james$ curl http://localhost:5601/api/status
    ```


## Reference

#### Elastic Stack
  * [Register Elastic Certified Engineer](https://training.elastic.co/exam/elastic-certified-engineer)
  * [Run the Elastic Stack on Docker](https://www.elastic.co/guide/en/elastic-stack-get-started/master/get-started-docker.html)
  * [The definitive guide](https://www.elastic.co/guide/en/elasticsearch/guide/current/index.html)
  * [Elasticsearch reference](https://www.elastic.co/guide/en/elasticsearch/reference/7.2/index.html)
  * [`FAQ`](https://www.elastic.co/training/certification/faq): Certification FAQ 
  
#### Docker  
  * [Docker Compose Command](https://docs.docker.com/compose/reference/overview/)
  * [Elasticsearch on docker](https://www.elastic.co/guide/en/elasticsearch/reference/7.2/docker.html)






[elk-stack]: https://www.elastic.co/elk-stack
[stack-features]: https://www.elastic.co/products/stack

[config-es]: ./elasticsearch/config/elasticsearch.yml
[config-kbn]: ./kibana/config/kibana.yml
[config-ls]: ./logstash/config/logstash.yml
