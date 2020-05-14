# Rancher Logging

* Installs [Fluentd](https://www.fluentd.org/) and flexvolume log driver to collect container logs in Rancher

## Introduction

This chart bootstraps a [Fluentd](https://www.fluentd.org/) daemonset and a [Log-Aggregator](https://github.com/rancher/log-aggregator) flexvolume on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.
It's use for sends logs to log target config in rancher.

## Prerequisites
  - Rancher 2.1+

## 自定义 fluentd 配置路径

以下为日志收集中 fluentd 配置的相关默认路径，如果主机对应路径有变化，请通过应答自定义主机路径。

### 主机路径

```bash
fluentd.cluster.dockerRoot=/var/lib/docker
fluentd.cluster.ssl=/fluentd/etc/config/ssl
fluentd.cluster.custom=/var/lib/rancher/fluentd/etc/config/custom
fluentd.cluster.varlogcontainers=/var/log/containers
fluentd.cluster.varlogpods=/var/log/pods
fluentd.cluster.rkelog=/var/lib/rancher/rke/log
fluentd.cluster.customlog=/var/lib/rancher/log-volumes
fluentd.cluster.fluentdlog=/var/lib/rancher/fluentd/log
fluentd.cluster.libsystemddir=/usr/lib64
```

### 容器路径

```bash
fluentd.container.dockerRoot=/var/lib/docker
fluentd.container.ssl=/fluentd/etc/config/ssl
fluentd.container.custom=/fluentd/etc/config/custom
fluentd.container.config=/fluentd/etc/config/precan
fluentd.container.entry=/fluentd/etc/config/entry
fluentd.container.varlogcontainers=/var/log/containers
fluentd.container.varlogpods=/var/log/pods
fluentd.container.rkelog=/var/lib/rancher/rke/log
fluentd.container.customlog=/var/lib/rancher/log-volumes
fluentd.container.fluentdlog=/fluentd/log
fluentd.container.libsystemddir=/host/lib
```