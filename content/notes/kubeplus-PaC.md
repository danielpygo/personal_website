---
title: "KubePlus notes Pt. 2"
date: 2019-1-12T20:55:46-06:00
description: "Notes about KubePlus system"
type: "notes"
draft: false
---
## What is CloudArk?


CloudArk is an API Management software , aiming to get Operators enterprise-ready. The vision is an open marketplace where companies can build their platform using a declarative format. CloudFormation, at Amazon, has grown to be highly useful because it provisions infrastructure using a single yaml file. Infrastructure-as-code. However one of the major drawbacks is vendor lock-in obviously. Enterprises want flexibility when planning for the future. Furthermore, it provisions only AWS services, limiting it significantly to the products that Amazon has built or chooses to build. And thus, could lag behind the cutting edge and the newest softwares on Github.
Large enterprise companies planning ahead, might want to look elsewhere.


## What about Kubernetes?


First and foremost, there are many cloud services that offer Kubernetes. From DigitalOcean, to Amazon, to Google and more. In spite of this, Kubernetes itself does NOT solve vendor lock-in.


## What is Kubernetes?


Kubernetes manages and orchestrates small ephemeral units called Containers. The nature of Containers is ephemeral and stateless. A REST API could run in one of these, however this rest API is often bound to a database service on the cloud. There are many of such bindings, that essentially locks-in a piece of software to a specific cloud company.  So, as a result, Kubernetes, this great piece of software, has a problem with Statefulness. Keeping the application state of a Database like Redis, is much more complex than keeping a number of replicas for an nginx app. Stateful is difficult, Stateless is not.


## Enter Operators


There has been a lot of official support from CoreOS and others for a new Kubernetes paradigm called Operators. Kubernetes has controllers and resources to ensure a declarative state. Operators are custom-built controllers paired with custom resources that require domain-knowledge to build.
They are extensions to the official Kubernetes API; They can leverage the power of Kubernetes, along with a lot of the tooling and support that normal controllers and resources have.
The controller ensures that Kubernetes ensures a specific state for stateful applications, so they are providing Statefulness to Kubernetes itself.


If you think about it, these operators are doing the exact same function as Amazon S3, Amazon RDS. While Kubernetes provisions the servers and nodes, so does Amazon RDS.


What CloudArk provides is the opportunity to specify a Web Application’s tech stack or platform in a single declarative format. Platform as code. While CloudFormation provides Infrastructure as Code (for instance, the file might say, give me three AWS Elastic search server, three AWS RDS mysql server, etc), CloudArk does a similar thing (give me a prometheus operator, a mysql operator, a kafka operator, an elasticsearch operator and a tensorflow operator).


Do you see why there is overlap between the two? There is a corporate MongoDB service Mongodb Cloud Services and also an kubernetes mongodb operator. There is a corporate tensorflow service like Cloud ML and also an kubernetes tensorflow operator.


This is because both of these are Stateful applications. While some companies choose to make a service layer above the mongodb source code, or a service layer on top of the prometheus source code, others use their domain knowledge to create a mongodb operator or a prometheus operator. For example, an apache spark contributor on Github, Yinan Li, has taken her domain expertise to create Google’s spark-on-k8s-operator, but she very well could be hired tomorrow by Amazon EMR and do a fantastic job for their inbuilt service.


In this sense, Kubernetes, a piece of software used on many different cloud services, just got a whole lot more interesting with CloudArk.


## What is my own vision ?

We have already got proof of concept and have solved some challenging problems so far and are working on the first use-case. Right now, there are three three stateless API containers that interact with each other to deploy a number of Operators using Helm. But this is all done on the command line. The customer deploys our pod, and our API will deploy the Operators and expose some useful information about the composition of the Operator itself.


But I have a vision for this idea that includes a beautiful and fast website component, that serves as a dashboard for software and devops engineers. It has options for which cloud service to deploy to - a couple buttons AWS, GCP, Azure, DigitalOcean, etc. The website could tell the Developers information about the Custom Resources themselves, and what parameters or configuration options are included in the operator source code.


From the Software Engineering perspective, they go to the web app for documentation about the Operators we support, for guides/tutorials, and lastly to the dashboard for easy information about key information they need for developing their app. What was the database ip again?
Devops engineers would go to the website and use the dashboard and buttons to deploy or remove any operator they wish. They can rapidly change their tech stack.
