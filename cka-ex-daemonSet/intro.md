
<br>

# What is daemonSet 
A daemonset is a Kubernetes workload that runs on all nodes in a cluster. Daemonsets are used to run applications that need to be running **on every node** , such as system services or logging agents.

Daemonsets are defined using the DaemonSet API object. The DaemonSet object specifies the name of the pod template to use, as well as the selector that determines which nodes the pods should be scheduled on.

When a DaemonSet is created, Kubernetes will create a pod for each node that matches the selector. The pods will be created in a rolling fashion, so that only one pod is created on a node at a time.

The DaemonSet object also specifies a strategy field, which defines how the pods are updated. The default **strategy** is `RollingUpdate`, which updates the pods in a rolling fashion.

Daemonsets are a powerful tool for running applications that need to be running on every node in a cluster. They are easy to use and can be used to manage a variety of different applications.

Summary: the ds is to add a missing feature for each Node.

# common daemonset in kubernetes

The most common DaemonSets you'll see are:

* Metrics exporters (node-exporter, kube-state-metrics)
* Log collectors (fluentd, logstash)
* DNS server (CoreDNS) -- use to resolve , pod.ns or service.ns 
* Network policies (kube-proxy, calico-node)
* Resource metrics API (metrics-server)

# What's new in recent release
few updates for daemonset in recent Kubernetes releases.

> Kubernetes 1.21 was released on February 22, 2022.
> Kubernetes 1.24 was released on June 15, 2022.

In Kubernetes 1.20, daemonsets now support the updateStrategy field, which allows you to specify how daemonsets are updated. You can choose between a RollingUpdate strategy, which updates daemonsets in a rolling fashion, or a Recreate strategy, which recreates all daemonsets at once.

In Kubernetes 1.21, daemonsets now support the podDisruptionBudget field, which allows you to specify a PodDisruptionBudget for your daemonset. A PodDisruptionBudget is a mechanism to prevent disruption to your daemonset by limiting the number of pods that can be unavailable or evicted at any given time.

In Kubernetes 1.22, daemonsets now support the topologySpreadConstraints field, which allows you to control how pods are spread across nodes in your cluster. This can be useful for ensuring that your daemonsets are evenly distributed across your cluster, or for avoiding placing pods on nodes with specific hardware or software requirements.

In Kubernetes 1.27 , Removal of DaemonSetUpdateSurge feature gate.
