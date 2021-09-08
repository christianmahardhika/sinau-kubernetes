# Flux CD

## Install Flux

```
brew install fluxctl
```

## Create a Kubernetes namespace for Flux

```
kubectl create namespace flux
```

## Generate Flux manifest files

```
fluxctl install --git-user=christianmahardhika --git-email=christianmahardhika@users.noreply.github.com --git-url=git@github.com:christianmahardhika/sinau-kubernetes --git-path=2-fluxcd/deployments --git-branch=main --namespace=flux > flux.yaml
```

## Apply manifest files

```
kubectl apply -f flux.yaml
```

## Verify deployment

```
kubectl get pods -n flux
```

## Retrieve SSH key via fluxctl

```
fluxctl identity --k8s-fwd-ns flux
```
