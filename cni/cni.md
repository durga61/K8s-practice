kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')&env.IPALLOC_RANGE=10.50.0.0/16"

by default, the range of IP addresses and the subnet used by weave-net is 10.32.0.0/12 and it's overlapping with the host system IP addresses.
To know the host system IP address by running ip a command :-