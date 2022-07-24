# Kafka-on-Kubernetes

# Kafka

Apache Kafka is a distributed publish-subscribe messaging system that receives data from disparate source systems and makes the data available to target systems in real time. Kafka is written in Scala and Java and is often associated with real-time event stream processing for big data.

Find more on https://kafka.apache.org/intro

# Kafka zookeeper

ZooKeeper is used in distributed systems for service synchronization and as a naming registry. When working with Apache Kafka, ZooKeeper is primarily used to track the status of nodes in the Kafka cluster and maintain a list of Kafka topics and messages.

# Kubernetes

Kubernetes is a portable, extensible, open source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

Find more on https://kubernetes.io/docs

# Kafka on Kubernetes

Here Goal is to deploy zookeeper and kafka in kubernetes in simple way for easy kafka server setup

Requirements : Kubectl installed and Kubernetes cluster configured. https://kubernetes.io/docs/tasks/tools/

# Steps

* Deploy Zookeeper in Kubernetes using zookeeper-deployment.yaml
      
      Kubectl apply -f zookeeper-deployment.yaml
      
* Deploy kafka-server in kubernetes using kafka-deployment.yaml
      
      Kubectl apply -f kafka-deployment.yaml
      
* Optionaly you can create services for each using zookeeper-service.yaml and kafka-service.yaml

      kubectl apply -f zookeeper-service.yaml
      kubectl apply -f kafka-service.yaml
      
* port-forward kafka-server to local
      
      * Get pod name using 
      Kubectl get pods
      * Port forward to local
      kubectl port-forward -n [namespace] [kafka-pod-name] 9092:9092


