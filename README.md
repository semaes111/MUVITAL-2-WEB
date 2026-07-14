# MÜV Vital Web

Sitio web estático de MÜV Vital, club privado de salud y rendimiento en Roquetas de Mar (Almería).

## Estructura

```text
.
├── index.html                  # Página principal
├── legal.html                  # Aviso legal, privacidad y cookies
├── support.js                  # Runtime requerido por la exportación
├── images/                     # Logotipos e imágenes optimizadas WebP/PNG
└── docs/
    ├── brand/                  # Guía de color de la marca
    └── reference/              # Capturas conceptuales de referencia
```

La raíz del repositorio es también la raíz pública del sitio. No hay una fase de compilación ni dependencias locales que instalar.

## Vista previa local

El runtime debe servirse por HTTP; no se recomienda abrir `index.html` directamente con `file://`.

```bash
python3 -m http.server 4173
```

Después, abre `http://localhost:4173`.

## Despliegue

Publica el contenido de la raíz en el directorio público del alojamiento (`public_html` en una instalación estándar de Hostinger). El documento de entrada es `index.html`.

El sitio utiliza recursos externos en tiempo de ejecución:

- Google Fonts para Playfair Display y Source Sans 3.
- React 18.3.1, ReactDOM 18.3.1 y Babel Standalone 7.29.0 desde `unpkg.com`, cargados por `support.js` con comprobación SRI.

## Estado funcional antes de producción

- El formulario valida los datos y muestra una confirmación, pero la exportación original no envía la solicitud a ningún backend. Debe conectarse a un endpoint o servicio de formularios antes de captar solicitudes reales.
- `legal.html` conserva el marcador `«PENDIENTE: email-contacto»`; debe sustituirse por la dirección definitiva del responsable.
- No se incluyen claves, credenciales ni variables de entorno.

## Marca

La web aplica la paleta y los logotipos del material entregado. La guía se conserva en `docs/brand/muv-colores.pdf`; las capturas de referencia están en `docs/reference/` y no forman parte del despliegue funcional.

