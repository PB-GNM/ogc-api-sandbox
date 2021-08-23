# Demo service for pygeoapi with INSPIRE harmonized Statistical Units for the Netherlands

This service is a copy of https://github.com/Geonovum/ogc-api-sandbox/tree/main/services/pygeoapi
It has been made to find out issues that can be encountered while publishing an INSPIRE harmonized dataset.
There is a link with https://github.com/Geonovum/OAPIF-PDOK-INSPIRE which does basicaly the same together with the Dutch hosting organisation PDOK.

## Technical info

Runs latest GitHub `main` branch of `pygeoapi` using
its [Docker Image from DockerHub](https://cloud.docker.com/u/geopython/repository/docker/geopython/pygeoapi).
with a [local config file](local.config.yml).

## Deployment

This service is automatically (re)deployed if anything within this directory or its subdirs changes
when committed/pushed.

A GitHub Action invokes an Ansible Playbook.
See the following deployment files:

* [GitHub Action](../../.github/workflows/deploy.pygeoapi.yml)
* [Ansible Playbook](../../ansible/deploy.yml)

The Ansible Playbook can also be invoked directly.
 
## New Service from Duplication

Creating a new service `xyz` via duplication of this directory:

* duplicate this and name it as the service e.g. `services/xyz`
* create GitHub Action file as copy/rename from [GitHub Action](../../.github/workflows/deploy.pygeoapi.yml) to `deploy.xyz.yml`
* new 3 lines for `xyz` in [Ansible Playbook](../../ansible/deploy.yml)
* the variables, mainly `SERVICE_NAME=xyz` in [env.sh](env.sh).
* adapt at least `url:` (line 5) in [local.config.yml](local.config.yml)
