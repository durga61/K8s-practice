## mocks

1. Deploy a pod named nginx-pod using the nginx:alpine image.

2. Get the list of nodes in JSON format and store it in a file at /opt/outputs/nodes-z3444kd9.json.

. kubectl get nodes -o json > /opt/outputs/nodes-z3444kd9.json

1. Use JSON PATH query to retrieve the osImages of all the nodes and store it in a file /opt/outputs/nodes_os_x43kj56.txt.
        kubectl get nodes -o jsonpath='{.items[*].status.nodeInfo.osImage}' > /opt/outputs/nodes_os_x43kj56.txt
The osImages are under the nodeInfo section under status of each node.