###kubectl cmds

# kubectl apply -f pod.yml

# kubectl get nodes

# kubectl get pods

# kubectl get pods -o wide



# kubectl run ngnix --image=nginx

# kubectl apply -f pod.yml

# kubectl describe pod nginx

# kubectl edit pod nginx

# kubectl delete pod  nginx


## diff between RC and RS

# ReplicaSet has option  selector which can match pod , but why do you have to provide selector when you have provided the pod definition under template
# RS can match pod which are not created by RS definition or pods which exist before RS definition

## kubectl create -f rs-definition.yml

## kubectl get replicaset

## kubectl delete replicaset myapp-replicaset

## scale - update replace no and  re-run  definition yml

## kubectl replace -f rs-definition.yml

## kubectl scale --replicas=6 -f rs-definition.yml

## Deployment

# Recreate - destroys current version of pods and brings up new version  
# this leads application downtime and inaccessible to users  during downtime

# Rolling update - defaulat deployment strategy -   rollout one by one and brings dwon current pod one by one

# check rollout status - kubectl rollout status deploymnent/myapp-deployment 
# check rollout histroy - kubectl rollout history deploymnent/myapp-deployment 

# how do you upgrade appliation - by changing imageid in deployment yml file  and run 
# kubectl create -f deployment-defi.yml

