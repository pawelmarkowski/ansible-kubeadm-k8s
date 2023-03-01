# ansible-cf.kubeadm

Create k8s with kubeadm

error during init:

Unfortunately, an error has occurred:
 timed out waiting for the condition

This error is likely caused by:
 - The kubelet is not running
 - The kubelet is unhealthy due to a misconfiguration of the node in some way (required cgroups disabled)

If you are on a systemd-powered system, you can try to troubleshoot the error with the following commands:
 - 'systemctl status kubelet'
 - 'journalctl -xeu kubelet'

Additionally, a control plane component may have crashed or exited when started by the container runtime.
To troubleshoot, list all containers using your preferred container runtimes CLI.
Here is one example how you may list all running Kubernetes containers by using crictl:
 - 'crictl --runtime-endpoint unix:///run/containerd/containerd.sock ps -a | grep kube | grep -v pause'
 Once you have found the failing container, you can inspect its logs with:
 - 'crictl --runtime-endpoint unix:///run/containerd/containerd.sock logs CONTAINERID'
