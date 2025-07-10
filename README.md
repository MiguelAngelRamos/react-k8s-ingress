# Enunciado: Despliegue de React en Kubernetes con Namespace, Resources y HPA

## Objetivo
Configurar el despliegue de una aplicación React en Kubernetes siguiendo buenas prácticas de organización y escalabilidad.

## Requerimientos

1. **Namespace**: Crea un namespace personalizado para aislar los recursos de la aplicación.
2. **Deployment**:
   - El deployment de React debe estar dentro del namespace creado.
   - Debe iniciar con **1 réplica** (un solo pod).
   - Agrega la sección de `resources` para limitar y solicitar recursos (CPU y memoria) para el contenedor.
3. **Service**:
   - El servicio debe estar en el mismo namespace y exponer el deployment.
4. **HPA (Horizontal Pod Autoscaler)**:
   - Crea un HPA asociado al deployment, con un umbral de utilización de CPU del **50%**.
   - El HPA debe permitir escalar entre **1 y 10 pods**.
5. **Asociación de recursos**: Todos los manifiestos deben estar asociados al namespace creado.

## Entregables
- Archivos YAML para:
  - Namespace
  - Deployment (con resources)
  - Service
  - HPA

## Notas
- Recuerda aplicar los manifiestos en el orden correcto: namespace, deployment, service, hpa.
- Puedes usar `kubectl apply -f <archivo>` para cada manifiesto.
- Verifica el escalado automático generando carga sobre la aplicación.
