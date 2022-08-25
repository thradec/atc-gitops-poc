# atc-gitops-poc

```
$ kubectl create namespace argocd
$ kubectl create namespace crossplane-system

$ kubectl apply -n argocd -f mngt-cluster/argocd/argocd.yaml
$ kubectl apply -n crossplane-system -f mngt-cluster/crossplane-system/crossplane.yaml

$ kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
$ kubectl -n argocd port-forward svc/argocd-server 8080:443

$ kubectl -n crossplane-system create secret generic aws-creds --from-file creds=./aws-creds.conf
```