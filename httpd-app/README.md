# Aplicación HTTPD para ArgoCD

Esta es una aplicación de ejemplo que despliega un servidor Apache HTTP (httpd) usando ArgoCD para la gestión GitOps.

## Estructura del Proyecto

- `/application.yaml`: Definición de la aplicación ArgoCD
- `/k8s/`: Directorio con los manifiestos de Kubernetes
  - `deployment.yaml`: Despliega el servidor httpd
  - `service.yaml`: Expone el servidor httpd dentro del clúster
  - `configmap.yaml`: Contiene el HTML personalizado para la página de inicio

## Cómo Desplegar

Para desplegar esta aplicación con ArgoCD, sigue estos pasos:

1. Asegúrate de tener ArgoCD instalado en tu clúster Kubernetes
2. Aplica el archivo `application.yaml` en tu clúster:

```bash
kubectl apply -f application.yaml
```

3. La aplicación se sincronizará automáticamente desde el repositorio Git

## Configuración

Puedes personalizar la página HTML editando el ConfigMap en `k8s/configmap.yaml`.

## Notas

- Esta aplicación está configurada para autohealing y prune automático
- La aplicación se desplegará en el namespace por defecto
- ArgoCD creará el namespace si no existe
