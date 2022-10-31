## create a environment variable outside the pod definition and inject it 

1. imperative 
2. Declarative

## imperative 

kubectl create configmap webapp-config-map --from-literal=APP_COLOR=darkblue

kubectl create configmap game-config-2 --from-file=configure-pod-container/configmap/game.properties

## Declarative

 kubectl create -f configMap.yml

 kubectl get configMaps

 kubectl describe configMaps

