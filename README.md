# Dockerfile Maven Build for OODT (Sample Project)
[GSoC 2019 Project]


## Overview
This sample project was generated using RADIX archetype of Apache OODT, and aims to integrate a docker build/deploy process into the maven build/deploy process of OODT projects by the end of its development.
The first commit contains the files generated from the RADIX Archetype 1.2.5.


## Development Plan
* Integrate dockerfile-maven plugin.
* Configure dockerfile-maven plugin to generate a docker image at '''install''' stage of maven.
* Add means to deploy the generated docker images to DockerHub (or an equivalent docker image repository) at the '''deploy''' stage of maven.

Once this project is stable, Voila! We have a fresh deployment system for an Apache OODT project!


## Requirements
* Java Development Kit (JDK) 1.6+
* JAVA_HOME set

## Installation
* Build OODT
  $ mvn clean package **[ARGS]**

* Deploy OODT
  $ tar zxf distribution/target/${PROJECT_ARTIFACT_ID}-distribution-*-bin.tar.gz -C /my/deployment/directory/oodt

* Run OODT
  $ cd /my/deployment/directory/oodt
  $ cd bin
  $ ./oodt start


---
NOTE: For other build configurations, add the following arguments:
(default)           : bin, crawler, data, extensions,
                      filemgr (Lucene), logs, pcs, resmgr,
                      tomcat, workflow, pge

-Pfm-solr-catalog   : default components, filemgr (Solr),
                      solr, tomcat/webapps/solr
