# QualityOps

Repositorio privado de la plataforma QualityOps.

## Estado actual

La migración está **bloqueada hasta recuperar el paquete fuente original** `QualityOps_current_package(2).zip`.

Actualmente el repositorio contiene:

- `assets/css/qualityops-design-system.css`
- documentación del proceso
- una validación automática del baseline

Todavía faltan:

- `qualityops.html` completo (el original tenía aproximadamente 789 KB)
- `assets/brand/qualityops-favicon.svg`
- `assets/brand/favicon-32.png`
- `assets/brand/favicon-16.png`
- `assets/brand/qualityops-apple-touch-icon.png`
- `assets/brand/qualityops-logo-dark.svg`
- `assets/brand/qualityops-pdf-logo-light.png`

El fragmento Base64 incompleto usado durante el primer intento de migración fue retirado del árbol activo. No puede reconstruirse el ZIP porque solo llegó el primer fragmento.

## Validación automática

El workflow `.github/workflows/validate-migration.yml` comprueba que:

- estén presentes todos los archivos requeridos;
- `qualityops.html` no esté vacío ni truncado;
- no se publiquen fragmentos temporales bajo `.import/`.

La validación permanecerá en rojo deliberadamente mientras falte el paquete fuente. No debe omitirse ni marcarse la migración como completada para silenciarla.

## Dependencias externas detectadas

El HTML original utilizaba desde jsDelivr:

- `html2canvas@1.4.1`
- `jspdf@2.5.1`

Cuando se recupere el HTML, estas dependencias deben validarse y fijarse mediante un mecanismo reproducible antes del despliegue.

## Seguridad y conservación

La revisión inicial no detectó claves Stripe, JWT de Supabase, claves AWS ni patrones evidentes de secretos en los archivos disponibles.

Hasta establecer un baseline funcional no se debe rediseñar ni refactorizar el frontend. La prioridad es conservar fielmente el original y verificar navegación, assessment, resultados y exportación PDF.

## Próximo paso obligatorio

Recuperar o volver a adjuntar `QualityOps_current_package(2).zip`. Después:

1. importar `qualityops.html` íntegro;
2. restaurar o sustituir explícitamente los assets ausentes;
3. ejecutar la validación y comprobar el frontend;
4. revisar secretos y dependencias;
5. continuar con arquitectura, autenticación y despliegue.
