##How to install kubectl##

1. Downloan the binary

```bash
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
```

2. Assign permission

```bash
chmod +x ./kubectl
```

3. Move binary file, to make it can execute every where

```bash
sudo mv ./kubectl /usr/local/bin/kubectl
```

4. Verify

```bash
kubectl version
```
