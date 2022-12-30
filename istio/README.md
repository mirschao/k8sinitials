# istio install

### unzip istio tarball.
```shell
tar xf istio-1.16.1-linux-amd64.tar.gz -C /usr/local/
```

### setting ENV profile
```shell
vim /etc/profile.d/istio.sh
export PATH=$PATH:/usr/local/istio-1.16.1/bin
source /etc/profile
```

### istio install to k8scluster
```shell
istioctl install --set profile=default -y
✔ Istio core installed
✔ Istiod installed
✔ Ingress gateways installed
✔ Installation complete                 Making this installation the default for injection and validation.
Thank you for installing Istio 1.16.
Please take a few minutes to tell us about your install/upgrade experience!  https://forms.gle/99uiMML96AmsXY5d6
```

### set NAMESPACE to automatically inject Envoy sidecar proxie
```shell
kubectl label namespace NAMESPACE istio-injection=enabled
```
