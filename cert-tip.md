## Here's a tip!

As you might have seen already, it is a bit difficult to create and edit YAML files. Especially in the CLI. During the exam, you might find it difficult to copy and paste YAML files from browser to terminal. Using the kubectl run command can help in generating a YAML template. And sometimes, you can even get away with just the kubectl run command without having to create a YAML file at all. For example, if you were asked to create a pod or deployment with specific name and image you can simply run the kubectl run command.

Use the below set of commands and try the previous practice tests again, but this time try to use the below commands instead of YAML files. Try to use these as much as you can going forward in all exercises

Reference (Bookmark this page for exam. It will be very handy):

https://kubernetes.io/docs/reference/kubectl/conventions/

### Create an NGINX Pod

kubectl run nginx --image=nginx

Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)

kubectl run nginx --image=nginx --dry-run=client -o yaml

### Create a deployment

kubectl create deployment --image=nginx nginx

Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)

kubectl create deployment --image=nginx nginx --dry-run=client -o yaml

Generate Deployment YAML file (-o yaml). Don't create it(--dry-run) with 4 Replicas (--replicas=4)

kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml

Save it to a file, make necessary changes to the file (for example, adding more replicas) and then create the deployment.

kubectl create -f nginx-deployment.yaml

OR

In k8s version 1.19+, we can specify the --replicas option to create a deployment with 4 replicas.

kubectl create deployment --image=nginx nginx --replicas=4 --dry-run=client -o yaml > nginx-deployment.yaml



kubectl create deployment --image=httpd:2.4-alpine httpd-frontend --replicas=3 --dry-run=client -o yaml > /root/httpd-deployment.yml


## exercise 

kubectl run --image=nginx:alpine nginx-pod

kubectl run --image=redis:alpine redis --dry-run=client -o yaml > redis-pod.yml

and edit yml file add labels

## export port 

Create a service redis-service to expose the redis application within the cluster on port 6379.

kubectl expose pod redis --port=6379 --name redis-service


Create a deployment named webapp using the image kodekloud/webapp-color with 3 replica

 kubectl create deployment --image=kodekloud/webapp-color webapp --replicas=3


Create a new namespace called dev-ns.

kubectl create namespace dev-ns

reate a new deployment called redis-deploy in the dev-ns namespace with the redis image. It should have 2 replicas.


kubectl create deployment redis-deploy --image=redis --namespace=dev-ns --dry-run=client --replicas=2 -o yaml > deploy.yml

kubectl apply -f deploy.yml 

 kubectl get deployments.apps -n dev-ns


kubectl scale deployment or kubectl edit deployment