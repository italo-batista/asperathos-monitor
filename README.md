# Asperathos - Monitor
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Overview
The **Monitor** is responsible for gather, calculate and publish metrics collected from applications (e.g.: application progress) or environment resources (e.g.: CPU usage).
The Asperathos Controller and Rebalancer services can use these metrics to take decisions to meet some QoS requirements, but the Monitor is not dependent of these other approaches.
It is possible, for example, to develop a plugin that only capture metrics from the usage of some VM resource to ease its visualization for Ops teams.

**Asperathos** was developed by the [**LSD-UFCG**](https://www.lsd.ufcg.edu.br/#/) *(Distributed Systems Laboratory at Federal University of Campina Grande)* as one of the existing tools in **EUBra-BIGSEA** ecosystem.

**EUBra-BIGSEA** is committed to making a significant contribution to the **cooperation between Europe and Brazil** in the *area of advanced cloud services for Big Data applications*. See more about in [EUBra-BIGSEA website](http://www.eubra-bigsea.eu/).

To more info about Monitor and how does it works in **BIGSEA Asperathos environment**, see [details.md](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/details.md) and [asperathos-workflow.md](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/asperathos-workflow.md).

## How does it works?
The monitor is implemented following a **plugin architecture**, allowing the service to monitor different types of application and different metrics of interest related to the user needs, as QoS requirements or resources managing. 

## How to develop a plugin?
See [plugin-development.md](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/plugin-development.md).

## Requirements
* Python 2.7
* Linux packages: python-dev and python-pip
* Python packages: setuptools, tox and flake8

To **apt** distros, you can use [pre-install.sh](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/pre-install.sh) to install the requirements.

## Install
Clone the [Monitor repository](https://github.com/bigsea-ufcg/bigsea-monitor.git) in your machine.

### Configuration
A configuration file is required to run the Monitor. **Edit and fill your monitor.cfg in the root of Monitor directory.** Make sure you have fill up all fields before run.
You can find a template in [config-example.md](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/config-example.md). 

### Run
In the Monitor root directory, start the service using run script:
```
$ ./run.sh
```

Or using tox command:
```
$ tox -e venv -- monitor
```

## Monitor REST API
Endpoints are avaliable on [restapi-endpoints.md](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/restapi-endpoints.md) documentation.

## Avaliable plugins
* [Spark Sahara](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/plugins/spark_sahara.md)
* [Spark Mesos](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/plugins/spark_mesos.md)
* [Openstack Generic](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/plugins/openstack_generic.md)
* [Web Application](https://github.com/bigsea-ufcg/bigsea-monitor/tree/master/docs/plugins/web_app.md)
