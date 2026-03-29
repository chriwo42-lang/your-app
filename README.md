# your-app

Test-App für das GitOps-Setup auf OpenShift.  
Wird über ArgoCD aus `ocp-workloads` deployt.

## Helm Chart

```
helm/
├── Chart.yaml
├── values.yaml
└── templates/
    ├── deployment.yaml
    ├── service.yaml
    └── route.yaml
```

## Konfiguration

Alle Werte in `helm/values.yaml` können beim Deploy überschrieben werden.  
Environment-spezifische Overrides liegen in `ocp-workloads/apps/project-a/your-app/`.

| Parameter | Default | Beschreibung |
|---|---|---|
| `replicaCount` | `2` | Anzahl Pods |
| `image.repository` | `quay.io/openshift/origin-hello-openshift` | Container Image |
| `image.tag` | `latest` | Image Tag |
| `service.port` | `8080` | Service Port |
| `route.enabled` | `true` | OpenShift Route anlegen |
| `route.tls` | `true` | TLS Edge Termination |
