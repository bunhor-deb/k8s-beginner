# kubectl Cheatsheet

A short reference for common `kubectl` commands, flags and examples.

## Basics

- Show cluster and client version:

```
kubectl version --client
kubectl version --short
```

- List resources (default namespace):

```
kubectl get pods
kubectl get svc
kubectl get deployments
```

- List resources in a specific namespace:

```
kubectl get pods -n my-namespace
```

## Inspect resources

- Describe a resource (detailed status and events):

```
kubectl describe pod my-pod -n my-namespace
```

- Get YAML/JSON for automation or inspection:

```
kubectl get deployment my-deploy -n default -o yaml
kubectl get pod -o json
```

## Create / Update / Delete

- Apply a manifest (create or update):

```
kubectl apply -f ./my-manifest.yaml
```

- Delete resources from a file or by name:

```
kubectl delete -f ./my-manifest.yaml
kubectl delete pod my-pod -n default
```

## Debugging & Logs

- Fetch logs from a pod (single container):

```
kubectl logs my-pod
```

- Tail logs and follow:

```
kubectl logs -f my-pod
```

- Exec into a container (interactive shell):

```
kubectl exec -it my-pod -- /bin/sh
```

## RBAC & Permissions

- Check if current user can perform an action:

```
kubectl auth can-i create pods -n default
```

- List Roles/ClusterRoles and RoleBindings:

```
kubectl get role -n default
kubectl describe role pod-reader -n default
kubectl get clusterrole
kubectl get rolebinding -n default
```

## Contexts & kubeconfig

- Show current context and kubeconfig:

```
kubectl config current-context
kubectl config view --minify
```

- Use a specific context or kubeconfig file:

```
kubectl --context=my-cluster get nodes
kubectl --kubeconfig=path/to/config get pods
```

## Output formatting

- Common `-o` formats:

```
- json   # machine-readable
- yaml   # human + machine
- wide   # table with extra columns
- name   # resource type/name, useful for scripts
```

Example:

```
kubectl get pods -o wide
kubectl get pods -o jsonpath='{.items[*].metadata.name}'
```

## Quick tips

- Use `-n <namespace>` to scope commands to a namespace.
- Use `kubectl explain <resource>` to learn resource fields (`kubectl explain deployment.spec`).
- For automation, prefer `-o yaml`/`-o json` and `kubectl apply -f -` with stdin.

---

This file is a minimal cheatsheet — tell me if you want it expanded with examples for Deployments, Services, Ingress, or RBAC manifests.
