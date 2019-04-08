---
title: "Kubernetes notes"
date: 2018-11-12T20:55:46-06:00
description: "Notes about kubernetes system"
type: "notes"
draft: false
---
[KubePlus](https://itnext.io/evolution-of-paases-to-platform-as-code-in-kubernetes-world-74464b0013ca)
  * CaaS avoids vendor lock-in
  * advanced capabilities of containerized elements not possible
  * Kubeplus extends kubernetes with operators, different than PaaS approach
  * Operators extend Kubernetes API to manage software for queues, databases.  Self-assemble these
  * Devops constructs custom PaaS, provisions, .yamls
  * Application Developer declares and creates application platforms as code leveraging custom resources introduced by the installed Operators.? So to find credentials the app developer may want to go and discover Postgres instances, he logs in and interacts.

  * What is the role of these helm charts in all of this? for operators. Why use them for operators.

OPERATOR CRD
Operator manager takes from kubectl new operator, polls it, parses the url and put sit in the etcd. Deployer reads chart URL, then calls helm and deploys the chart, results sent back to deployer, step 7 puts things back in etcd. Operator details docs,
Discovery api server polling etcd, to find the docs, then it registers the endpoints 
