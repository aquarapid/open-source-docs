# Vitess operator overview

This document describes the purpose of the Vitess operator for Kubernetes and introduces its usage. To learn more about Vitess, see the [Vitess documentation](https://vitess.io/docs). 

## The Vitess operator automates the management of Vitess on Kubernetes.

[Running Vitess on Kubernetes](https://vitess.io/docs/get-started/kubernetes/) using a Helm chart provides automated deployment, machine management, and networking configuration. However, this pattern still requires significant maintenance tasks, like planned failover and reparenting, updates, and resharding. The purpose of the Vitess operator is to automate much of that maintenance work.

The Vitess operator automates tasks like these:

+ Deploy any number of Vitess clusters, cells, keyspaces, shards, and tablets to scale both reads and writes either horizontally or vertically;
+ Deploy overlapping shards for Vitess resharding, allowing zero-downtime resizing of shards;
+ Trigger manual planned failover via Kubernetes annotation;
+ Replicate data across multiple Availability Zones in a single Kubernetes cluster to support immediate failover of read/write traffic to recover from loss of an Availability Zone;
+ Automatically roll out updates to Vitess-level user credentials.

## Deploy a cluster from a configuration file.

The configuration for your Vitess cluster is recorded in a single configuration file. The operator treats your Vitess configuration as a [custom resource](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/). To deploy a cluster, customize the configuration file and apply it with `kubectl`.

## Maintain your Vitess cluster by updating your configuration file.

The operator implements applied changes in the configuration file for your Vitess cluster.

## The Vitess operator is open source.

The Vitess operator is on [GitHub](https://github.com/planetscale/vitess-operator). See the repository for information on licensing and contribution.

<!--## See also-->

<!-- At some point, we will need to add links to the deployment how-to and the API reference here. -->
