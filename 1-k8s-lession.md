# Kubernetes for the Absolute Beginner

## 1. Kubernetes Architecture

**What is Node?**

> A node is a worker machine, physical or virtual, on which Kubernetes is installed. And that is where containers will be launched by Kubernetes. It was also know as minions in the past.

**What is Cluster?**

> A cluser is a set of nodes grouped together. This way, even if one node fails, you have your application still accessible from the other nodes. Moreover, having multiple nodes helps in sharing load as well.

**What is Master?**

> The master is another node with the Kubernetes installed in it and is configured as a master. The master watches over the nodes in the cluster and it responsible for the actual orchestration of containers on the worker notes.

**## Components ##**

> When you install Kubernetes on a system, you;re actually installing all this components _API Server, etcd, kubelet, Container Runtime, Controller, Scheduler._

> _- API Server_
>
> > The API Server acts as the Frontend for Kubernetes. The users, management devices, command-line interfaces all talk to the API Server to interact with a Kubernetes cluser.

> _- etcd (Key-value store)_
>
> > etcd is a distributed reliable ke value store use by Kubernetes to store all data used to manage the cluster.
>
> > Think of it like this, When you have multiple nodes and multiple masters in your cluster, etcd stores all that information on all the nodes in the cluster in a distributed manner. ectd is responsile for implementing logs withing the cluster to ensure that there are no conflicts between the masters.

> _- Scheduler_
>
> > The scheduler is responsible for distributing work or containers across multiple nodes. It looks for newly created containers and assigns them to nodes.

> _- Controller_
>
> > The controllers are the brain behind orchestration. They're responsible for noticing and responding when nodes container or endpoints goes donwn. The controllers make decisions to bring up new containers, in such cases.

> _- Container Runtime_
>
> > The container runtime is the underlying software that is used to run containers.

> _- kubelet_
>
> > Kubelete is the agent that runs on each node in the cluster. This agent is responsible for making sure that the container are running on the nodes as expected.

**What is pods?**

> A pod is a single instance of an application, it is the smallest object that we can create in Kubernetes.
