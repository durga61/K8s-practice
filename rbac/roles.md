kubectl create role developer --namespace=default --verb=list,create,delete --resource=pods


kubectl create rolebinding dev-user-binding --namespace=default --role=developer --user=dev-user
