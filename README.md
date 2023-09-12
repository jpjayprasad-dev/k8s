# Backend Core Deployment

## Use Kubernetes to deploy enviornmental variables used by web-app
```kubernetes
kubectl apply -f ./aiot-portal/secret.yml
kubectl create -f ./aiot-portal/config_map.yml
```
## Use Kubernetes to create persistan-volume, persistant-volume-claim deployment and service resources for postgres database
```kubernetes
kubectl apply -f ./aiot-portal/postgres/*.yml
```
## Use Kubernetes to create deployment and service resources for django app
```kubernetes
kubectl apply -f ./aiot-portal/django/component-django.yml
```
## Use Kubernetes to create ingress resources for django app
```kubernetes
kubectl apply -f ./aiot-portal/ingress-service.yml
```

# Agent Deployment

## Use Kubernetes to deploy enviornmental variables used by the agents
```kubernetes
kubectl create -f ./aiot-agent/config_map.yml
```
## Use Kubernetes to create Kafka Brokers and Zookeeper
```kubernetes
kubectl apply -f ./aiot-agent/kafka.yml
kubectl apply -f ./aiot-agent/zookeeper.yml
```
## Use Kubernetes to create deployment of the agent
```kubernetes
kubectl apply -f ./aiot-agent/agent-deploy.yml
```

# Chatbot Deployment

## Use Kubernetes to deploy enviornmental variables used by the chatbot
```kubernetes
kubectl create -f ./aiot-chat/config_map.yml
kubectl create -f ./aiot-chat/secret.yml
```
## Use Kubernetes to create Elasticsearch Cluster
```kubernetes
kubectl apply -f ./aiot-chat/elasticsearch.yml
```
## Use Kubernetes to create deployment and service of the chatbot
```kubernetes
kubectl apply -f ./aiot-chat/chatbot-deploy.yml
