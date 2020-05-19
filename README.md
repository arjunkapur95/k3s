k3s - Lightweight Kubernetes
===============================================

Lightweight Kubernetes.  Easy to install, half the memory, all in a binary less than 100 MB.


Quick-Start - Install Script
--------------

The k3s `install.sh` script provides a convenient way for installing to systemd or openrc,
to install k3s as a service just run:

```bash
curl -sfL https://get.k3s.io | sh -
```

A kubeconfig file is written to `/etc/rancher/k3s/k3s.yaml` and the service is automatically started or restarted.
The install script will install k3s and additional utilities, such as `kubectl`, `crictl`, `k3s-killall.sh`, and `k3s-uninstall.sh`, for example:

```bash
sudo kubectl get nodes
```

`K3S_TOKEN` is created at `/var/lib/rancher/k3s/server/node-token` on your server.
To install on worker nodes we should pass `K3S_URL` along with
`K3S_TOKEN` or `K3S_CLUSTER_SECRET` environment variables, for example:

```bash
curl -sfL https://get.k3s.io | K3S_URL=https://myserver:6443 K3S_TOKEN=XXX sh -
```


