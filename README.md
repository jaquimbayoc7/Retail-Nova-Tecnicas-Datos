# RetailNova · Técnicas Avanzadas de Datos — Talleres 1, 2 y 3

Talleres resueltos del caso **RetailNova** (Maestría en Computación para Desarrollo de Apps Inteligentes): arquitectura de datos, modelo dimensional con SCD tipo 2 y Data Vault con arquitectura Medallion en PostgreSQL. Se entrega como un sitio web estático e interactivo.

## Contenido

El proyecto cuenta una sola historia en tres talleres: **decidir** la arquitectura (Taller 1), **modelar** las ventas (Taller 2) y **construir** el Data Vault en PostgreSQL (Taller 3).

**Navegación de la página**
- **Story time:** 11 escenas con una gráfica animada cada una, desde los requerimientos hasta el Data Vault (botones, flechas del teclado o puntos de la línea de tiempo).
- **Conclusiones por taller:** una gráfica explorable por taller (puntajes por momento, quejas vs. modelo, crecimiento del Vault por lote).
- **Menú lateral:** acordeón por taller con progreso de lectura y botones «Ver» para mostrar solo un taller (Historia, T1, T2, T3 o Cierre) con botones de anterior/siguiente.

| Taller | Tema | Qué se ve en la página |
|---|---|---|
| 1 · Semana 1 | Arquitectura y ciclo de vida del dato | Clasificación de 15 fuentes, recorrido de 3 preguntas de negocio, ETL vs ELT con 10 filas del POS, matrices de decisión (hoy, Año 2, Año 5) y 7 diagramas interactivos. |
| 2 · Semana 2 | Modelado dimensional | Filtro de las 18 tarjetas hecho/dimensión, elección del grano, esquema estrella en SVG, estrella vs copo de nieve, simulador de SCD tipo 1 y 2, aditividad y respuesta a las 4 quejas. |
| 3 · Semana 3 | Data Vault 2.0 y Medallion | Capas Bronze/Silver/Gold, diagrama interactivo del Raw Vault, bitácora de los 3 lotes con la historia de Ana, `gold.dim_cliente` con SCD tipo 2, reportes «ciudad al comprar» vs «ciudad actual», auditoría y recomendación. |

| Ruta | Descripción |
|---|---|
| [index.html](index.html) | Página principal con navegación lateral y tema claro/oscuro. |
| [Taller1_RetailNova_Resuelto.pdf](Taller1_RetailNova_Resuelto.pdf) | Taller 1 resuelto. |
| [Taller2_RetailNova_Resuelto.pdf](Taller2_RetailNova_Resuelto.pdf) | Taller 2 resuelto. |
| [Taller3_RetailNova_DataVault_Resuelto.pdf](Taller3_RetailNova_DataVault_Resuelto.pdf) | Taller 3 resuelto. |
| [diagramas/](diagramas/) | Siete diagramas HTML autocontenidos del Taller 1 (d1 a d7), incrustados en la página por `iframe`. |

## Tecnología

HTML, CSS y JavaScript puros, sin dependencias, sin build y sin servidor. Los diagramas del Taller 1 son archivos HTML autocontenidos incrustados con `iframe`; los esquemas de los talleres 2 y 3 son SVG dentro de `index.html`.

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
