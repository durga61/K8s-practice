# Upgrade

kubectl drain node01 --ignore-daemonsets  # evict all pods fom node1 , pods terminated gracefully and scheduled on another nod

kubectl uncordon node-1  # after node comes up , pods will not be scheduled until it is uncordon

kubectl cordon node-2 # It stops new pods pods being scheduled on node-2, it does not evict pods on node-2

kubectl drain node01 --ignore-daemonsets --force   delete pods which are not managed by rs

## K8s releases

Kube-api v1.10 X                                kubectl (X+1, X, X-1)

controll-manger kubescheduler (x-1)
v1.9 or v.10     v1.9 or v.10

kubelet      kubeproxy  (x-2)
v1.8 or v1.9 or v1.10

K8s support upto 3 minor version

if current verions is 1.13, it  supports v.13, v1.12, v.11

upgrade one version at a time

current version v1.11, target is v1.13
## upgrade process

on prem

kubeadm upgrade plan

kubeadm upgrade apply

to upgrade kubeadm has to be upgraded first

apt-get update -y kubeadm=1.12.0-00

kubeadm upgrade apply v1.12.0

apt-get upgrade -y kubelet=1.12.0-00

kubeadm upgrade node config --kubelet-version v1.12.0

systemctl restart kubelet

ssh to node
update and upgrade 
apt update && apt install kubeadm=1.20.0-00 && kubeadm upgrade node
