---
title: Annotations and labels
weight: 1000
---



## Annotations

The Vault Operator supports annotating most of the resources it creates using a set of fields in the Vault Specs:

### Common Vault Resources annotations

```yaml
apiVersion: "vault.banzaicloud.com/v1alpha1"
kind: "Vault"
metadata:
  name: "vault"
    spec:
      annotations:
          example.com/test: "something"
```

These annotations are common to all Vault created resources

- Vault StatefulSet
- Vault Pods
- Vault Configurer Deployment
- Vault Configurer Pod
- Vault Services
- Vault Configurer Service
- Vault TLS Secret

### Vault StatefulSet Resources annotations

```yaml
apiVersion: "vault.banzaicloud.com/v1alpha1"
kind: "Vault"
metadata:
  name: "vault"
    spec:
      vaultAnnotations:
          example.com/vault: "true"
```

These annotations are common to all Vault StatefulSet created resources

- Vault StatefulSet
- Vault Pods
- Vault Services
- Vault TLS Secret

These annotations will override any annotation defined in the common set

### Vault Configurer deployment Resources annotations

```yaml
apiVersion: "vault.banzaicloud.com/v1alpha1"
kind: "Vault"
metadata:
  name: "vault"
    spec:
      vaultConfigurerAnnotations:
          example.com/vaultConfigurer: "true"
```

These annotations are common to all Vault Configurer Deployment created resources

- Vault Configurer Deployment
- Vault Configurer Pod
- Vault Configurer Service

These annotations will override any annotation defined in the common set

### ETCD CRD Annotations

```yaml
apiVersion: "vault.banzaicloud.com/v1alpha1"
kind: "Vault"
metadata:
  name: "vault"
    spec:
      etcdAnnotations:
          etcd.database.coreos.com/scope: clusterwide
```

These annotations are set *only* on the etcdcluster resource

### ETCD PODs Annotations

```yaml
apiVersion: "vault.banzaicloud.com/v1alpha1"
kind: "Vault"
metadata:
  name: "vault"
    spec:
      etcdPodAnnotations:
          backup.velero.io/backup-volumes: "YOUR_VOLUME_NAME"
```

These annotations are set *only* on the etcd pods created by the etcd-operator

## Labels

The Vault Operator support labelling most of the resources it creates using a set of fields in the Vault Specs:

### Vault StatefulSet Resources labels

```yaml
apiVersion: "vault.banzaicloud.com/v1alpha1"
kind: "Vault"
metadata:
  name: "vault"
    spec:
      vaultLabels:
          example.com/log-format: "json"
```

These labels are common to all Vault StatefulSet created resources

- Vault StatefulSet
- Vault Pods
- Vault Services
- Vault TLS Secret

### Vault Configurer deployment Resources labels

```yaml
apiVersion: "vault.banzaicloud.com/v1alpha1"
kind: "Vault"
metadata:
  name: "vault"
    spec:
      vaultConfigurerLabels:
          example.com/log-format: "string"
```

These labels are common to all Vault Configurer Deployment created resources

- Vault Configurer Deployment
- Vault Configurer Pod
- Vault Configurer Service
