# Ambassador API Gateway with Flux

This repo can deploy an install Ambassador on GKE using fluxd with manifestGeneration set to true. Flux will generate the manifests using Kustomize and deploy the Kubernetes resources.

You can generate the manifests by running the following command.

```
$ kustomize build deploy/
```

The deployed service will bind to NodePort 30000. You can then use an HTTP/S Load Balancer on the service to route traffic.

## Repository structure

```
.
├── .flux.yaml
├── README.md
├── base
│   ├── ambassador
│   │   ├── ambassador-crds.yaml
│   │   ├── ambassador-ingress.yaml
│   │   ├── ambassador-rbac.yaml
│   │   ├── ambassador-service.yaml
│   │   └── kustomization.yaml
│   └── kustomization.yaml
└── deploy
    └── kustomization.yaml
```