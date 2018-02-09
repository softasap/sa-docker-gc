sa-docker-gc
============

[![Build Status](https://travis-ci.org/softasap/sa-docker-gc.svg?branch=master)](https://travis-ci.org/softasap/sa-docker-gc)

Installs shell batch to clean up docker images and containers on your docker server, see https://github.com/spotify/docker-gc


Usage example:

```YAML

     - {
         role: "sa-docker-gc"
       }

```


```YAML

vars:

my_docker_gc_exclude:
  - "adminer:latest"
  - "alpine:3.5"
  - "container-conductor-ubuntu-xenial:0.9.2"
  - "debian:jessie"
  - "mysql:5.7"
  - "nginx:1.12-alpine"
  - "postgres:9.4"
  - "rabbitmq:3.6.12-alpine"
  - "softasap/ubuntu:16.04"
  - "ubuntu:16.04"
  - "uifd/ui-for-docker:latest"

# /etc/docker-gc-exclude-containers

my_docker_gc_exclude_containers:
 - "docker_ui"
 - "ui-for-docker"


roles:

     - {
         role: "sa-docker-gc",
         docker_gc_exclude: "{{my_docker_gc_exclude}}",
         docker_gc_exclude_containers: "{{my_docker_gc_exclude_containers}}"
       }

```



Usage with ansible galaxy workflow
----------------------------------

If you installed the sa-docker-gc  role using the command


`
   ansible-galaxy install softasap.sa-docker-gc
`

the role will be available in the folder library/sa-docker-gc

Please adjust the path accordingly.

```YAML

     - {
         role: "softasap.sa-docker-gc"
       }

```



Copyright and license
---------------------

Code is dual licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) and the [MIT License] (http://opensource.org/licenses/MIT). Choose the one that suits you best.

Reach us:

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)

Join gitter discussion channel at [Gitter](https://gitter.im/softasap)

Discover other roles at  http://www.softasap.com/roles/registry_generated.html

visit our blog at http://www.softasap.com/blog/archive.html
