[![Build Status](https://travis-ci.org/microservices-demo/microservices-demo.svg?branch=master)](https://travis-ci.org/microservices-demo/microservices-demo)

# Sock Shop : A Microservice Demo Application

The application is the user-facing part of an online shop that sells socks. It is intended to aid the demonstration and testing of microservice and cloud native technologies.

It is built using [Spring Boot](http://projects.spring.io/spring-boot/), [Go kit](http://gokit.io) and [Node.js](https://nodejs.org/) and is packaged in Docker containers.

### Architecture

![Architecture diagram](https://github.com/microservices-demo/microservices-demo.github.io/blob/HEAD/assets/Architecture.png "Architecture")

You can read more about the [application design](./internal-docs/design.md).

## Deployment Steps

### 1. Clone the repo

Clone the repo locally. In a terminal, run:

```
$ git clone https://github.com/omarfoz/microservices-demo
```

### Run the application on Kubernetes


## Prerequisites

1. [Create an account with IBM Cloud](http://ibm.biz/micro-reg)

2. [Install IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started)

3. Log into your IBM Cloud account 
```
$ ibmcloud login 
```

Select eu-gb for UK region or to know your region click [here](https://console.bluemix.net/iam/#/users/) 
then click your account name then click Cloud Foundry access then you will see organization name and your regions.

4. Install the Container Service plug-in.
```
$ ibmcloud plugin install IBM-Containers -r Bluemix
```

5. [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl)

6. Create cluster
```
ibmcloud ks cluster-create --name YOUR_CLUSTER_NAME
```
NOTE: It can take a few minutes for your cluster to be ready

7. Configure Kubernetes cluster
```
$ ibmcloud ks cluster-config YOUR_CLUSTER_NAME
```

Copy and paste response in CLI.
NOTE: in Windows OS the response start with "SET" 


The [deploy folder](./deploy/) contains scripts and instructions to provision the application onto your favourite platform. 

8. Go to the deploy/kubernetes folder
```
$ cd deploy/kubernetes
```
9. Create namespace sock-shop
```
$ kubectl create namespace sock-shop

```
10. Deploy to Kubernetes Cluster
```
$ kubectl apply -f complete-demo.yaml
```

11 Get the public IP address for a worker node in the cluster
```
$ ibmcloud ks workers <cluster_name>
```
12 Access the microservices application
```
http://<Public IP>:30001/
```
Please let us know if there is a platform that you would like to see supported.

## Bugs, Feature Requests and Contributing

We'd love to see community contributions. We like to keep it simple and use Github issues to track bugs and feature requests and pull requests to manage contributions. See the [contribution information](.github/CONTRIBUTING.md) for more information.

## Screenshot

![Sock Shop frontend](https://github.com/microservices-demo/microservices-demo.github.io/raw/master/assets/sockshop-frontend.png)


## 
