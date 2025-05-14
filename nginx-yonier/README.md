# Nginx para YonierPro

Esta es una aplicación de ejemplo que despliega Nginx en el namespace `yonierpro-dev`.

## Características

- Sincronización manual (no automática)
- Namespace personalizado: yonierpro-dev
- ConfigMap para personalizar la página de inicio
- Servicio ClusterIP para acceso interno

## Uso

Para sincronizar manualmente esta aplicación después de cambios, use:

```bash
argocd app sync yonierpro-app
```

## Notas

Esta aplicación se despliega desde el repositorio https://github.com/YonierGomez/mcp-argocd-test.git