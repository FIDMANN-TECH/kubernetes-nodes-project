# 🧩 Working with Kubernetes Nodes

## 📌 Project Overview

This project introduces the concept of **Kubernetes Nodes**, which are the worker machines responsible for running containerized workloads in a Kubernetes cluster.

Using **Minikube**, this project provides a beginner-friendly, hands-on approach to understanding how nodes operate, how workloads are scheduled on them, and how DevOps engineers inspect, manage, and troubleshoot node-level resources.

---

## 🎯 Project Objectives

By the end of this project, learners will have:

- Understood what Kubernetes nodes are and their role in a cluster
- Explored node components and metadata
- Learned how pods are scheduled onto nodes
- Practiced inspecting node health and resources
- Gained hands-on experience using `kubectl` to manage nodes
- Applied real-world DevOps troubleshooting techniques

---

## 🧠 Key Concepts Covered

- Kubernetes Nodes (Worker Nodes)
- Control Plane vs Worker Nodes
- Node status and conditions
- Pod scheduling
- Node resource inspection
- Labels and selectors
- Basic troubleshooting

---

## 🛠️ Technologies Used

- Kubernetes
- Minikube
- kubectl
- Docker
- Linux (Ubuntu / Xubuntu)

---

## 📁 Project Structure

```text
kubernetes-nodes-project/
├── README.md
└── img
```

## Areas for Improvement & Troubleshooting

This section demonstrates controlled troubleshooting scenarios commonly
encountered in Kubernetes environments. Issues were intentionally simulated
in a safe manner to validate diagnosis and recovery procedures.

---

### Metrics API Not Available

#### Issue
An attempt to retrieve node resource metrics using the command below initially
failed:

```bash
kubectl top nodes
The cluster returned the following error:

arduino
Copy code
Metrics API not available
This indicated that the Kubernetes Metrics API was not yet exposed to the
cluster, preventing access to CPU and memory usage statistics.


Resolution
The issue was resolved by enabling the Metrics Server addon in Minikube:

bash
Copy code
minikube addons enable metrics-server
After allowing sufficient time for the addon to initialize, node metrics
became available.

Verification
The command was re-run successfully:

bash
Copy code
kubectl top nodes
This confirmed that the Metrics API was operational and resource metrics
were accessible.
```


### Key Takeaway
This troubleshooting exercise demonstrates an understanding of Kubernetes
observability components, specifically the role of the Metrics Server in
providing cluster resource insights. It also highlights a structured
approach to identifying issues, applying corrective actions, and validating
successful recovery.


## 🏁 Conclusion

This project provides a solid foundation for understanding Kubernetes nodes and how workloads are scheduled and managed.
It reflects real-world DevOps practices and prepares learners for more advanced Kubernetes administration and cloud-native deployments.

## Below are screenshots of workflow:
![minikube-cluster](./img/01_minikube_cluster_running.png)
![list-k8s-node](./img/02_list_kubernetes_nodes.png)
![node-description](./img/03_node_detailed_description.png)
![node-condition](./img/04_node_conditions_ready.png)
![pod-schedule-on-node](./img/05_pod_scheduled_on_node.png)
![node-resource-usage](./img/06_node_resource_usage.png)
![node-labels](./img/07_node_labels.png)
![custom-node-label](./img/08_custom_node_label.png)
![pod-assigned-via-selector](./img/09_pod_assigned_via_selector.png)
![node-troubleshooting-example](./img/10_node_troubleshooting_example.png)
![metrics-server-not-available](./img/11_metrics_server_not_available.png)
![metrics-server-restored](./img/12_metrics_server_restored.png)

