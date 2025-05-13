# Aplicación Nginx para ArgoCD

Esta aplicación despliega un servidor Nginx en el namespace `demo` utilizando ArgoCD.

## Componentes

- **Deployment**: Despliega un pod con Nginx 1.25
- **Service**: Expone el Nginx dentro del cluster
- **ConfigMap**: Contiene el HTML personalizado para la página principal

## Instalación

Para instalar esta aplicación con ArgoCD, aplica el archivo `application.yaml`:

```bash
kubectl apply -f application.yaml
```

La aplicación se desplegará automáticamente en el namespace `demo` (este se creará automáticamente si no existe).

## Acceso

Una vez desplegada, puedes acceder al servicio Nginx dentro del cluster con:

```bash
kubectl port-forward -n demo svc/nginx 8080:80
```

Y luego navega a http://localhost:8080 en tu navegador.
