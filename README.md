# How to install cview-issuer via helm chart

- [How to install cview-issuer via helm chart](#how-to-install-cview-issuer-via-helm-chart)
  - [Add helm chart repository](#add-helm-chart-repository)
  - [Check actual version](#check-actual-version)
  - [Check all versions](#check-all-versions)
    - [Install on kubernetes](#install-on-kubernetes)
    - [Install on Openshift](#install-on-openshift)

## Add helm chart repository
```console
helm add repo dror1966 https://dror1966.github.io/cview-issuer-chart/
```
## Check actual version
```console
helm repo update dror1966
```
<pre>
NAME                    CHART VERSION   APP VERSION     DESCRIPTION
dror1966/cview-issuer   0.0.29          0.0.29          C-View issuser plugin for cert-manager
</pre>

## Check all versions
```console
helm search repo cview-issuer
```
<pre>
NAME                    CHART VERSION   APP VERSION     DESCRIPTION
dror1966/cview-issuer   0.0.29          0.0.29          C-View issuser plugin for cert-manager
dror1966/cview-issuer   0.0.28          0.0.28          C-View issuser plugin for cert-manager
</pre>

```console
helm search repo cview-issuer --versions 
```

### Install on kubernetes 

```console
helm install \
  cview-issuer dror1966/cview-issuer \
  --namespace cview-issuer \
  --create-namespace \
  --version 0.0.29 \
  --set crd.install=true

```

### Install on Openshift 

```console
helm install \
  cview-issuer dror1966/cview-issuer \
  --namespace cview-issuer \
  --create-namespace \
  --version 0.0.29  \
  --set crd.install=true \
  --set openshift.enabled=true

```


