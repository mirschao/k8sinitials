# install argocd

```shell
k create ns argocd
k apply -f install.yaml -n argocd
k patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
k -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64
install -m 555 argocd-linux-amd64 /usr/local/bin/argocd
```
