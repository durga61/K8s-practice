## Node port

# Node port expoese port on nodes and forward that request to underlying pods on the nod

## Cluster IP

Default service created on cluster launch

# Cluster IP is useful in micro service environment where Cluster IP provides a virtual IP/name using which pods communicates with front end / back end
#  without bothering about underling pods 


access using service name or cluser ip

##  LB

# provides a external IP to custer / end user which send request to underlying nodes which runs our pods


kubectl get services
 

 kubectl describe service

# check services from other pod

k run curl --image=alpine/curl --rm -it -- sh

curl service-name


Print the names of all deployments in the admin2406 namespace in the following format:
DEPLOYMENT CONTAINER_IMAGE READY_REPLICAS NAMESPACE
<deployment name> <container image used> <ready replica count> <Namespace>
. The data should be sorted by the increasing order of the deployment name.

Example:
DEPLOYMENT CONTAINER_IMAGE READY_REPLICAS NAMESPACE
deploy0 nginx:alpine 1 admin2406
Write the result to the file /opt/admin2406_data.



kubectl -n admin2406 get deployment -o custom-columns=DEPLOYMENT:.metadata.name,CONTAINER_IMAGE:.spec.template.spec.containers[].image,READY_REPLICAS:.status.readyReplicas,NAMESPACE:.metadata.namespace --sort-by=.metadata.name > /opt/admin2406_data