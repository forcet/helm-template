# Helm Chart – Aplicación (frontend / backend / data / mongo)

Este chart despliega una aplicación compuesta por varios servicios internos y un frontend expuesto al exterior.  
Incluye:

- `Deployment` o `StatefulSet` (configurable)
- `ConfigMap` y `Secret`
- `HorizontalPodAutoscaler` (HPA)
- `NetworkPolicy` para segmentar tráfico interno
- `Service` (ClusterIP / headless para StatefulSet)
- `Route` (OpenShift) opcional para el frontend

## Arquitectura lógica

```text
mongo (StatefulSet)  <--  backend-data  <--  backend-api  <--  frontend  <-- Internet
