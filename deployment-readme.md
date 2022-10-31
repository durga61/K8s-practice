## create
# kubectl create -f deployment-app.yml

## get/statu deployment

# kubectl get deployments

## update 

# kubectl apply -f deployment-app.yml

or 

# kubectl edit deployment frontend and update image tag , it does update file 

kubectl edit deployment frontend     or   update yaml file and apply file again


## deployment trigger rollout and you can status and history of rollout
## check status/rollout

# kubectl rollout status deployent/deploymnet-app
# kubectl rollout history deployent/deploymnet-app

# kubectl rollout undo depolyment/myapop-deployment


## how rollout and rollback happens under hood

# well deployment objects create two replicasets , in one set it brings down pod simulteniously on the other replicaset brings up another pod

# incase of rollback, it drops pods in the latest replicatset and brings up pods in older replicaset 


# you can check this by kubectl get replicaset - you can observer two replicasets were created with same deployment objects 
