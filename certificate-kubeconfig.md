  #kubectl certificate approve akshay
  #kubectl get csr agent-smith -o yaml
  #kubectl certificate deny agent-smith
  #kubectl delete csr agent-smith




  #kubectl config --kubeconfig=/root/my-kube-config use-context research

  #kubectl config --kubeconfig=/root/my-kube-config current-context


# how to check autorization level


kubectl describe pod kube-apiserver-controlplane -n kube-system  , check  --authorization-mode=Node,RBAC



kubectl describe role kube-proxy -n kube-system   # describe role

kubectl describe rolebinding kube-proxy -n kube-system  # check which role assigned to user




To create a Role:- 

kubectl create role developer --namespace=default --verb=list,create,delete --resource=pods

edit role

kubectl edit role developer -n blue


To create a RoleBinding:- 

kubectl create rolebinding dev-user-binding --namespace=default --role=developer --user=dev-user


###

kind: Role
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  namespace: default
  name: developer
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["list", "create","delete"]

---
kind: RoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: dev-user-binding
subjects:
- kind: User
  name: dev-user
  apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: developer
  apiGroup: rbac.authorization.k8s.io