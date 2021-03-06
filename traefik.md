# Setup Traefik Kubernetes Ingress Controller

1. Clone this Repo
2. Change the toml config in the [traefik-config-map.yaml](traefik/traefik-config-map.yaml)
3. Apply Kustomization
    - For kubectl version 1.15 and above run `kubectl apply -k traefik`
    - Download and install [Kustomize](https://github.com/kubernetes-sigs/kustomize) then run `kustomize build traefik | kubectl apply -f -`


## Generate Self-Signed TLS Certificates Ingress (Optional)

```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout certs/tls.key -out certs/tls.crt -subj "/CN=minikube/O=minikube"
```