


export NAMESPACE=nodejs-webserver

kind create cluster --name nodejs-webserver

kubectl create namespace $NAMESPACE

kubectl -n $NAMESPACE apply -f deployment.yaml

kubectl -n $NAMESPACE apply -f service.yaml

kubectl -n $NAMESPACE port-forward service/nodejs-webserver 4000:80

