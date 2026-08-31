# QualityOps

Repositorio privado de la plataforma QualityOps.

## Estado de la migración

Migración iniciada desde el paquete fuente `QualityOps_current_package(2).zip`.

### Archivos fuente detectados

- `qualityops.html` (~789 KB)
- `assets/css/qualityops-design-system.css` (~13 KB)

El CSS ha sido importado como archivo nativo del repositorio.

El HTML principal no se ha modificado. La integración usada para esta migración no permite adjuntar directamente un archivo local de este tamaño en una sola operación; por ello **no debe considerarse completada la migración del HTML hasta que `qualityops.html` aparezca íntegro en la raíz del repositorio**.

## Incidencias del paquete de origen

El HTML referencia recursos de marca que no están incluidos en el ZIP recibido:

- `assets/brand/qualityops-favicon.svg`
- `assets/brand/favicon-32.png`
- `assets/brand/favicon-16.png`
- `assets/brand/qualityops-apple-touch-icon.png`
- `assets/brand/qualityops-logo-dark.svg`
- `assets/brand/qualityops-pdf-logo-light.png`

También utiliza dependencias externas desde jsDelivr:

- `html2canvas@1.4.1`
- `jspdf@2.5.1`

## Seguridad

La revisión inicial no detectó claves Stripe, JWT de Supabase, AWS keys ni patrones evidentes de API secrets en los dos archivos del paquete.

## Regla de conservación

Durante esta fase no se debe rediseñar ni refactorizar el frontend. La prioridad es preservar fielmente la versión HTML recibida antes de iniciar Cloudflare, Supabase, autenticación, leads o Stripe.

## Próximas fases

1. Completar importación íntegra de `qualityops.html`.
2. Recuperar los assets de marca ausentes.
3. Crear baseline verificable.
4. Validar frontend original.
5. Continuar con arquitectura y despliegue según la Master Build Specification.
