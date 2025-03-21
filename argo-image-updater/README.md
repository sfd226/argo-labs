# Argo image updater
kubectl -n argocd create secret generic git-creds --from-literal=username=udemy --from-literal=password=ghp_yyyyyy
kubectl patch application --type=merge -n argocd vote-staging --patch-file ../staging/argo_applications_vote-staging_patch.yaml
