# Helm config for starting webchat

### Code

Is available [here](https://github.com/14MR/chat-app) (forked and dockerized)

### Prerequirements

1. Kubernetes
1. Helm

### Installation


Create k8s cluster for Mongodb with replication:

    helm install --name my-mongodb stable/mongodb-replicaset

![](https://i.ibb.co/P6tRZZq/Screen-Shot-2019-11-01-at-21-26-54.png)

Make sure your pods' urls are the same as in`app/templates/deployment.yaml`

Create instance of the chat

    helm install --name chat ./app

Run command `export ...` showen in the logs

Then

    kubectl port-forward $POD_NAME 8080:80

enjoy
![](https://i.ibb.co/hfhpbpr/Screen-Shot-2019-11-01-at-21-05-55.png)
