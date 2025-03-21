kubectl create secret docker-registry -n argo docker-registry-creds --docker-server=https://index.docker.io/v1/ --docker-username=frederiquer --docker-password=whatever
kubectl create -f ./pv.yaml
kubectl create -f ./build-workflows-code.yaml

