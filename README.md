# RetailNova · Técnicas Avanzadas de Datos — Taller 1

Taller 1 resuelto para el caso **RetailNova**: fuentes de datos, ciclo de vida del dato, ETL vs ELT y arquitectura recomendada (lakehouse híbrido en el año 2 y Data Mesh en el año 5). Se entrega como un sitio web estático con diagramas interactivos.

## Contenido

| Ruta | Descripción |
|---|---|
| [index.html](index.html) | Página principal con las 5 actividades, entregables y navegación lateral (tema claro/oscuro automático). |
| [Taller1_RetailNova_Resuelto.pdf](Taller1_RetailNova_Resuelto.pdf) | Versión en PDF del taller resuelto. |
| [diagramas/d1-actual.html](diagramas/d1-actual.html) | Arquitectura actual: ETL nocturno hacia un data warehouse. |
| [diagramas/d2-recorrido-a.html](diagramas/d2-recorrido-a.html) | Pregunta A: ¿qué producto se agota primero en cada tienda? |
| [diagramas/d3-recorrido-b.html](diagramas/d3-recorrido-b.html) | Pregunta B: ¿se dañan productos por fallas en las neveras? |
| [diagramas/d4-recorrido-c.html](diagramas/d4-recorrido-c.html) | Pregunta C: ¿qué opinan los clientes de la marca propia Nova? |
| [diagramas/d5-etl-vs-elt.html](diagramas/d5-etl-vs-elt.html) | ETL frente a ELT sobre 10 filas crudas del POS. |
| [diagramas/d6-anio2-hibrida.html](diagramas/d6-anio2-hibrida.html) | Año 2: lakehouse con ingesta híbrida (ruta caliente y fría). |
| [diagramas/d7-anio5-mesh.html](diagramas/d7-anio5-mesh.html) | Año 5: Data Mesh sobre plataforma lakehouse común. |

## Tecnología

HTML, CSS y JavaScript puros, sin dependencias, sin build y sin servidor. Cada diagrama es un archivo HTML autocontenido que `index.html` incrusta mediante `iframe`.

## Ejecutar en local

Basta con abrir `index.html` en el navegador, o servir la carpeta:

```bash
python -m http.server 8000
# luego visitar http://localhost:8000
```

## Despliegue en Render

El repositorio incluye [render.yaml](render.yaml) (Blueprint) que define un **Static Site**; no requiere build ni variables de entorno.

### Opción A — Blueprint (recomendada)
1. Subir el repositorio a GitHub.
2. En [Render](https://dashboard.render.com): **New → Blueprint** y seleccionar este repositorio.
3. Confirmar el servicio `retail-nova-tecnicas-datos` y pulsar **Apply**.

### Opción B — Manual
1. **New → Static Site** y conectar el repositorio.
2. **Build Command:** *(vacío)* — **Publish Directory:** `.`
3. Pulsar **Create Static Site**.

Cada `git push` a `main` redespliega automáticamente. La página queda disponible en `https://retail-nova-tecnicas-datos.onrender.com` (o el nombre que Render asigne).

## Licencia

Ver [LICENSE](LICENSE).
