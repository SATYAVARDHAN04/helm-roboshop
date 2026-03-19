```bash
helm install nginx .
```

```bash
helm list
```

```bash
helm upgrade nginx .
```

```bash
helm status nginx
```

```bash
helm history nginx
```

```bash
helm upgrade nginx --description "upgrading to stabe nginx version" .
```

```bash
helm upgrade --install nginx --description "upgrading to stabe nginx version" .
```

```bash
helm rollback nginx # goes to previous version
```

```bash
helm rollback nginx 1 
```

```bash
helm uninstall nginx 
```

```bash
helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver
helm repo update
```

```bash
helm upgrade --install aws-ebs-csi-driver \
    --namespace kube-system \
    aws-ebs-csi-driver/aws-ebs-csi-driver
```

```bash
helm list --all-namespace
```

**REDIS INSTALLATION**

```bash
helm repo add bitnami https://charts.bitnami.com
```

```bash
helm repo update
```

```bash
helm install redis-cluster bitnami/redis
```