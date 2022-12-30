# install metrics-server
```shell
k apply -f components.yaml

vim /var/lib/kubelet/config.yaml
# append to "serverTLSBootstrap: true"

# setting all nodes.
systemctl daemon-reload
systemctl restart kubelet

# setting to all csr approved.
k get csr
k certificate approve csr-NAME

# visit metrics-server pod running?
k get pods -n kube-system | grep metrics
```
