## INSTALL EKSCTL FOR K8S CLUSTER CREATION

```bash
# for ARM systems, set ARCH to: `arm64`, `armv6` or `armv7`
ARCH=amd64
PLATFORM=$(uname -s)_$ARCH

curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"

# (Optional) Verify checksum
curl -sL "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_checksums.txt" | grep $PLATFORM | sha256sum --check

tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz

sudo install -m 0755 /tmp/eksctl /usr/local/bin && rm /tmp/eksctl
```

## INSTALL KUBECTL FOR K8S CLUSTER INTERACTION

```bash
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.33.3/2025-08-03/bin/linux/amd64/kubectl
```
```bash
chmod +x ./kubectl
```
```bash
sudo mv kubectl /usr/local/bin/kubectl
```

## NOW WE WILL CREATE A MANAGED NODE GROUP or IN SHORT A CLUSTER WITH A MASTER AND WORKER NODES

*NOTE: A MANAGED NODE GROUP IS THE SET OF AWS WORKER NODES(INSTANCES) THAT AWS WILL CREATE AND MANAGE ON ITS OWN*
```bash
eksctl create cluster --config-file=eks.yaml
```
```bash
eksctl delete cluster --config-file=eks.yaml


```bash
kubectl apply -f namespace.yaml
```

```
## KUBENS INSTALLATION

```bash
curl -sS https://webi.sh/kubens | sh; \
source ~/.config/envman/PATH.env
```

## INSTALL EBS DRIVERS

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
kubectl apply -f sc.yaml
```


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