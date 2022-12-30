# Install metallb prepares

### modify kube-proxy mode add ARP mode.
```shell
kubectl edit configmap -n kube-system kube-proxy

apiVersion: kubeproxy.config.k8s.io/v1alpha1
kind: KubeProxyConfiguration
mode: "ipvs"
ipvs:
  strictARP: true
```

### delete source keub-proxy.
```shell
kubectl -n kube-system delete pod kube-proxy-[*]
```

### install metallb controller.
```shell
kubectl apply -f metallb-native.yaml
```

### deploy ip pool configure.
```shell
kubectl apply -f metallb-ipool.yaml
```
