# atc-gitops-poc

```
$ kubectl create namespace argocd

$ kubectl apply -n argocd -f mngt-cluster/argocd/argocd.yaml

$ kubectl patch configmap/argocd-cm --type merge -p '{"data":{"application.resourceTrackingMethod":"annotation"}}' -n argocd

$ kubectl apply -n argocd -f mngt-cluster/argocd-apps/app-of-apps.yaml

$ kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d; echo

$ kubectl port-forward svc/argocd-server 8080:443 -n argocd

$ kubectl create secret generic aws-creds --from-file creds=./aws-creds.conf -n crossplane-system
```