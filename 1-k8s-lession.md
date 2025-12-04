# Kubernetes for the Absolute Beginner

## 1. Kubernetes Architecture

> **What is Node?**
> A node is a worker machine, physical or virtual, on which Kubernetes is installed. And that is where containers will be launched by Kubernetes. It was also know as minions in the past.

> **What is Cluster?**
> A cluser is a set of nodes grouped together. This way, even if one node fails, you have your application still accessible from the other nodes. Moreover, having multiple nodes helps in sharing load as well.

> **What is Master?**
> The master is another node with the Kubernetes installed in it and is configured as a master. The master watches over the nodes in the cluster and it responsible for the actual orchestration of containers on the worker notes.

> **What is pods?**
> A pod is a single instance of an application, it is the smallest object that we can create in Kubernetes.

> **What is kubectl?**
> kubectl is the Kubernetes command-line tool (client) used to interact with the Kubernetes API server. It translates user commands into API requests and displays or applies the results
> _Purpose_: Manage Kubernetes resources (create, update, delete, view) and inspect cluster state from a terminal.

> **What is replica?**
> A replica is one running instance (copy) of a Pod created from a Pod template. When you say “replicas: 3,” you are telling Kubernetes to ensure there are three separate Pod instances from that template running concurrently

> **Why replicas matter? (high level):**
> Availability: If one Pod or its node fails, other replicas keep the service available.
> Scalability: Multiple replicas let you handle more requests; a Service/load-balancer can distribute traffic across them.
> Fault tolerance & self-healing: Controllers recreate missing replicas automatically.

**## Components ##**

When you install Kubernetes on a system, you;re actually installing all this components _API Server, etcd, kubelet, Container Runtime, Controller, Scheduler._

> - _API Server:_ The API Server acts as the Frontend for Kubernetes. The users, management devices, command-line interfaces all talk to the API Server to interact with a Kubernetes cluser.

> - _etcd (Key-value store):_ etcd is a distributed reliable ke value store use by Kubernetes to store all data used to manage the cluster. Think of it like this, When you have multiple nodes and multiple masters in your cluster, etcd stores all that information on all the nodes in the cluster in a distributed manner. ectd is responsile for implementing logs withing the cluster to ensure that there are no conflicts between the masters.

> - _Scheduler:_ The scheduler is responsible for distributing work or containers across multiple nodes. It looks for newly created containers and assigns them to nodes.

> - _Controller:_ The controllers are the brain behind orchestration. They're responsible for noticing and responding when nodes container or endpoints goes donwn. The controllers make decisions to bring up new containers, in such cases.

> - _Container Runtime:_ The container runtime is the underlying software that is used to run containers.

> - _kubelet:_ Kubelete is the agent that runs on each node in the cluster. This agent is responsible for making sure that the container are running on the nodes as expected.

    ----------------------------------------
