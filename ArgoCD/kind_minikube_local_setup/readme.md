# If you are using Windows OS as I am follow the below steps to reproduce the environment

1. Instal WSL2 for Windows:
https://learn.microsoft.com/en-us/windows/wsl/install

2. On Powershell execute:
    ```
    wsl --install 
    ```

2. Install Docker
https://docs.docker.com/desktop/setup/install/windows-install/

3. Make sure Docker is running

4. Start your WSL. Open CMD and execute
    ```
    bash
    ```

5. Install minikube
    - Check your wsl architecutre with
    ```
    uname -m
    ```
    - To install the latest minikube stable release on x86-64 Linux using binary download:
    curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
    sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64

6. Start the Minikube cluster with 1 node
    ```
    minikube start
    ```

7. Start the Minikube cluster with 2 nodes
    ```
    minikube start --cpus=2 --memory=4096 --nodes=2
    ```


8. Check the cluster status
    ```
    kubectl cluster-info
    ```


9. Install kind

```
# For AMD64 / x86_64
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.26.0/kind-linux-amd64
# For ARM64
[ $(uname -m) = aarch64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.26.0/kind-linux-arm64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```

10. Create a kind cluster with one node
```
kind create cluster --name kind-demo
```