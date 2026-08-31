# QualityOps

Repositorio privado de la plataforma QualityOps.

## Baseline restaurado

La fuente verificada del paquete `QualityOps_SOURCE_ONLY_2026-08-30.zip` está disponible como:

- `qualityops.html`
- `assets/css/qualityops-design-system.css`

El HTML conserva el SHA-256 del archivo fuente recibido:

```text
68915941487f834713d6b3a119a23c720e754820f2365dcf4c7a088bd4368f33
```

La aplicación es un único frontend en HTML, CSS y JavaScript sin framework ni backend. Incluye landing, assessment de 18 preguntas, resultados, dashboard y generación de informe PDF.

## Identidad visual

La identidad visual se alineó con la referencia de marca aprobada: símbolo hexagonal con check, wordmark QualityOps bicolor, lema “ISO READINESS. SIMPLIFIED.”, navy profundo y azul eléctrico. La lógica funcional del baseline se conserva.

## Assets

La fotografía principal está embebida en el HTML como WebP data URI. El análisis de referencias del baseline no encontró dependencias hacia los antiguos paths `assets/brand/*`; por tanto, esos archivos no son necesarios para ejecutar esta versión restaurada.

El paquete fuente también incluye variantes de imágenes hero como material de respaldo, pero el baseline no depende de ellas.

## Dependencias externas

La generación de PDF usa:

- `html2canvas@1.4.1`
- `jspdf@2.5.1`

Ambas se cargan desde jsDelivr. La aplicación principal funciona sin red, pero la generación binaria del PDF necesita acceso a esas CDN mientras no se vendorizan las dependencias.

## Validación automática

El workflow `.github/workflows/validate-migration.yml` verifica:

- presencia del HTML y CSS;
- SHA-256 exacto del HTML;
- ausencia de fragmentos temporales bajo `.import/`;
- ausencia de rutas locales o temporales.

## Estado funcional conocido

Validado desde una extracción limpia del paquete fuente:

- landing, hero y navegación;
- onboarding y evaluación;
- 18 respuestas y cálculo de resultados;
- dashboard de resultados;
- presencia del generador PDF.

El PDF no pudo ejecutarse en la validación offline porque sus bibliotecas se cargan por CDN.

## Seguridad

El paquete y sus checksums fueron verificados antes de la importación. La revisión no encontró patrones evidentes de secretos ni rutas temporales en el HTML.

## Próximos pasos

1. Vendorizar o gestionar formalmente las dependencias de PDF.
2. Añadir pruebas de navegador reproducibles.
3. Definir hosting y cabeceras de seguridad.
4. Introducir backend, autenticación o pagos únicamente en fases separadas.

## Sitio web

El sitio se despliega automáticamente mediante GitHub Pages desde la rama `main`.
