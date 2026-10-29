# 12° Semana de Presupuesto y Derechos — ACIJ

Página de la 12° Semana de Presupuesto y Derechos de la Asociación Civil por la Igualdad y la Justicia (ACIJ). Reemplaza a https://acij.org.ar/semana-presupuesto-y-derechos/ y reúne el programa de actividades, los informes y el Monitor Presupuestario 2027.

Es una página estática, en un solo archivo (`index.html`) con sus imágenes en `assets/`. No necesita servidor ni compilación: se abre con doble clic.

## Estructura

```
index.html   la página (estilos, contenido y script)
assets/      imágenes de la identidad visual de la Semana
```

## Cómo cargar contenido

Todo lo que cambia durante la Semana está al principio del `<script>` de `index.html`, en el bloque **CONTENIDOS EDITABLES**. No hace falta tocar el resto del archivo.

- **`CONFIG.monitorURL`**: dirección del Monitor Presupuestario 2027 que se inserta en la sección "¿Qué cambia?" (hoy `https://monitor-2027.acij.org.ar/`).
- **`DOCUMENTOS`**: informes de la sección "Informes y análisis". Si `url` queda vacío, el informe aparece como "Próximamente".
- **`ACTIVIDADES`**: el programa. Cada fecha distinta genera su pestaña; los días no tienen que ser consecutivos.

### Campos de una actividad

| Campo | Para qué sirve |
|---|---|
| `inicio`, `fin` | Hora argentina, formato `'AAAA-MM-DDTHH:MM'`. Sin horario confirmado: sólo la fecha (`'AAAA-MM-DD'`) y aparece "Horario a confirmar". |
| `tipo`, `titulo`, `descripcion`, `lugar` | Textos de la tarjeta. |
| `organizan`, `participantes` | Opcionales. |
| `inscripcion` | Link de inscripción (se muestra hasta que la actividad termina). |
| `transmision` | Link de YouTube de la transmisión. |
| `publicacion` | Link al flyer (por ejemplo, el posteo de Instagram). |
| `agenda` | Programa detallado, desplegable: `{ hora, titulo, detalle, personas: [...], moderacion }`. |
| `materiales` | Lo que se suma cuando la actividad termina: `{ tipo, titulo, url }`. Tipos: `video`, `documento`, `presentacion`, `nota`, `fotos`, `enlace`. |

El estado de cada actividad (Próxima / En vivo / Finalizada) se calcula solo con la fecha y la hora. Los videos se muestran como material recién cuando la actividad terminó.

Un campo vacío (`''`) no se muestra.

## Publicar en WordPress

Subir `index.html` y la carpeta `assets/` manteniendo las rutas, o reemplazar las rutas `assets/...` por las URLs de la biblioteca de medios.
