# KCDA AFRICA FILES 

This are the files are used when creating an ingress controller

### Steps 

1. Run the ` kubectl create -f https://raw.githubusercontent.com/dmarinere/ingress-files/main/KCDA/ingress-controller.yaml ` command to create the ingress controller and other required components
2. Next we run this `kubectl run --image dmarinere/kcda-docker --port=8080 kcda ` to create a pod in kubernetes
3. A Cluster IP is create to expose the pod using `    kubectl expose pod kcda --port=80 --target-port=8080 ` our Pod runs on port 8080 and it is exposed on port 80 
4. Lastly we create the ingress resources to create a route to our Cluster IP service `kubectl create ingress demo --class=nginx  --rule="/=kcda:80"`


