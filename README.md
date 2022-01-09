# ansible-kubeadm-k8s

Based on https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/

## Start working after cluster installation

To start using your cluster, you need to run the following as a regular user:

mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

Alternatively, if you are the root user, you can run:

export KUBECONFIG=/etc/kubernetes/admin.conf

### Combine multiple config files into one

```bash
KUBECONFIG=$(echo $(find ~/.kube -iname "config-*") | sed 's/ /:/g') kubectl config view --raw > ~/.kube/config
```

## KUBEADM config files

https://kubernetes.io/docs/reference/config-api/kubeadm-config.v1beta3/#kubeadm-k8s-io-v1beta3-BootstrapTokenDiscovery


## Kubeadm without kube-proxy

https://docs.cilium.io/en/v1.10/gettingstarted/kubeproxy-free/#kubeproxy-free



## WIP: ToDo

helm installation
```bash
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```