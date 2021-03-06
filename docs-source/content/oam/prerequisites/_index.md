---
title: "Prerequisites"
weight: 1
pre : "<b>1. </b>"
description: "System requirements and limitations for deploying and running an OAM domain home"
---

### Introduction

This document provides information about the system requirements and limitations for deploying and running OAM domains with the Oracle WebLogic Server Kubernetes Operator 3.0.1.

In this release, OAM domains are supported using the “domain on a persistent volume”
[model](https://oracle.github.io/weblogic-kubernetes-operator/userguide/managing-domains/choosing-a-model/) only, where the domain home is located in a persistent volume (PV).

### System requirements for oam domains


* Kubernetes 1.16.0+, 1.17.0+, and 1.18.0+ (check with `kubectl version`).
* Flannel networking v0.9.1-amd64 or later (check with `docker images | grep flannel`).
* Docker 18.09.1+ or 19.03.1+ (check with `docker version`)
* Helm 3.1.3+ (check with `helm version`).
* You must have the `cluster-admin` role to install the operator.
* We do not currently support running OAM in non-Linux containers.
* A running Oracle Database 12.2.0.1 or later. The database must be a supported version for OAM as outlined in [Oracle Fusion Middleware 12c certifications](https://www.oracle.com/technetwork/middleware/fmw-122140-certmatrix-5763476.xlsx).

### Limitations

Compared to running a WebLogic Server domain in Kubernetes using the operator, the
following limitations currently exist for OAM domains:

* The "domain in image" model is not supported.
* Only configured clusters are supported.  Dynamic clusters are not supported for
  OAM domains.  Note that you can still use all of the scaling features,
  you just need to define the maximum size of your cluster at domain creation time.
* Deploying and running OAM domains is supported only with Oracle WebLogic Server Kubernetes Operator version 3.0.1
* The [WebLogic Monitoring Exporter](https://github.com/oracle/weblogic-monitoring-exporter)
  currently supports the WebLogic MBean trees only.  Support for JRF MBeans has not
  been added yet.

