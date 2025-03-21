# Change the password
kubectl create secret docker-registry -n argo-events docker-registry-creds --docker-server=https://index.docker.io/v1/ --docker-username=frederiquer --docker-password=whatever
# Change the user-id and the password in github-token-secret.yaml
kubectl create -f ./github-token-secret.yaml
