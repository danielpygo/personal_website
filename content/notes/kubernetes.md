---
title: "Kubernetes notes"
date: 2018-11-12T20:55:46-06:00
description: "Notes about kubernetes system"
type: "notes"
draft: false
---
[Kubernetes github guide](https://github.com/ajeetraina/kubernetes101)


## Ch1

Kubelet ensures containers are running and healthy

### PODS
  * multiple containers and storage vols
  * One deployment multiple pods
  * containers in the same pod has access to shared volume
  * pods are up and running until a controller destroys them
  * needs persistent storage they are ephemeral
### Deployments
  * Blueprint is a blueprint that deploys pods according to some spec
  * Sort of like an instance of a pod
  * Keep the pods running and update them in a controlled way
  * Resource usage can be specified
  * Inside the kubelet

### Secrets
  * An object where to store sensitive info like users and passwords
  * base64 encoded
  * refer to the secret in our pod
  * not encrypted, must use encryptionconfig

### Service
  * Responsible for mkaing pods discoverable inside the network or exposing to the internet
  * identifies pods by its labelselector
  * service has a reliable, nonchanging ip. think microservices

#### ClusterIP
  * deployment only visible inside the cluster

#### Node port
  * deployment only visible inside the cluster
  * deployment bound to a port of the master node
  * each node will proxy that port to your Service

#### Load balancer
  * gets a public ip assigned, http://:80
  * traffic loadbalanced between the pods of the deployment

### etc
  * Can scale up a deployment easily, deployments allow for
   rolling updates and scaling and replicasets. Services then grab
   these pods with selectors usually and expose them internally or externally.
   
### Daemon Set
  * A copy running on each of the nodes ,prometheus

### Job (there is also cronjob, parallel, non parallel)
  * RestartPolicy=OnFailure
  * Runs something ONCE. image processing
