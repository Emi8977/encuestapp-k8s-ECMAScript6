Proyecto CI/CD Otros repositorios relacionados:

    encuestapp-k8s-ECMAScript6
    encuestapp-env-argocd-ECMAScript6




Documentación del Repositorio Kustomize (Pipeline CI)

1. Estructura del Repositorio encuestapp-k8s

Este repositorio almacena los manifiestos de Kubernetes estructurados mediante Kustomize:

encuestapp-k8s-infra/
base/
    /deployment.yaml
    /service.yaml
    /kustomization.yaml
overlays/
    /dev/
        /patch-deployment.yaml
        /kustomization.yaml
    /stg/
        /patch-deployment.yaml
        /kustomization.yaml
    prod/
        /patch-deployment.yaml
        /kustomization.yaml


Contiene los manifiestos genéricos reutilizables para todos los entornos. No se deben definir versiones de imagen concretas aquí, sino usar una marca genérica como REPLACEME.

overlays/<env>/

Cada entorno tiene su carpeta dentro de overlays/. Define parches (patch-deployment.yaml) que modifican el manifiesto base con configuraciones específicas, como la versión de la imagen.
