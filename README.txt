# EUROCAR INTELLIGENCE — PWA

## Qué incluye
- Interfaz responsive para Safari iOS, iPad, Mac y Windows.
- Instalación como app web (PWA) cuando se sirve por HTTPS.
- Búsqueda y filtros sobre datos ficticios de demostración.
- Sección separada de subastas internacionales y directorio de portales.
- Favoritos guardados localmente en el dispositivo.
- Calculadora orientativa de coste y margen.

## Importante
Esta entrega NO recopila anuncios reales en directo. Las fichas son demostraciones y no deben confundirse con ofertas. Para un agregador real hace falta backend, base de datos, APIs/licencias/acuerdos con portales, tareas de actualización, deduplicación, conversión de moneda y reglas legales por país. No es correcto ni fiable hacer scraping indiscriminado de todos los portales.

## Probar en ordenador
Abre `index.html` directamente para probar la interfaz. Algunas funciones PWA requieren HTTPS o localhost.

## Publicar para Safari en iPhone
1. Sube todos los archivos de esta carpeta a un alojamiento web estático con HTTPS (por ejemplo, un hosting compatible con sitios estáticos).
2. Abre la dirección HTTPS en Safari en el iPhone.
3. Pulsa Compartir → Añadir a pantalla de inicio.
4. Activa “Abrir como app” si aparece esa opción y pulsa Añadir.

El service worker y el modo instalable necesitan HTTPS (excepto localhost). Abrir el HTML como archivo adjunto no instala una PWA.

## Para activar anuncios reales
Crear un servicio backend con conectores autorizados. Modelo sugerido:
- `listings`: fuente, URL original, ID externo, marca/modelo/versión, año, km, precio, moneda, país, imágenes permitidas, fecha de captura, estado.
- `auction_lots`: casa de subastas, lote, puja actual, cierre, comisiones, ubicación, condición/título.
- `price_history`: cambios observados con fecha.
- `users`, `favorites`, `saved_searches`, `alerts`.
- Normalización de moneda y unidades, deduplicación por VIN/ID externo y políticas de retención.
- Cada ficha debe enlazar al anuncio original y mostrar fuente y fecha de última actualización.

No se incluyen claves API ni acceso a cuentas. Deben configurarse de forma segura en el servidor, nunca dentro del HTML.
