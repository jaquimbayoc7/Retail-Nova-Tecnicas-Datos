# RetailNova · Técnicas Avanzadas de Datos — Talleres 1, 2 y 3

Sitio web estático e interactivo con el desarrollo completo del caso **RetailNova**, una cadena ficticia de 12 tiendas en el Valle del Cauca. Cuenta una sola historia en tres talleres: **decidir** la arquitectura de datos (Taller 1), **modelar** las ventas (Taller 2) y **construir** un Data Vault con arquitectura Medallion en PostgreSQL (Taller 3).

> Maestría en Computación para Desarrollo de Apps Inteligentes · Técnicas Avanzadas de Gestión de Datos
> **Integrante:** Julian Andres Quimbayo Castro · **Docente:** Ing. Alexander Yela Reyes

## Qué hay en la página

| Sección | Descripción |
|---|---|
| **Story time** | 11 escenas con una gráfica animada cada una, desde los requerimientos hasta el Data Vault. Se avanza con botones, flechas del teclado o la línea de tiempo. |
| **Hilo conductor** | Tabla que conecta cada decisión del Taller 1 con cómo se modeló en el 2 y cómo se construyó en el 3. |
| **Taller 1 · Arquitectura** | Clasificación de 15 fuentes, recorrido de 3 preguntas de negocio, ETL vs ELT con 10 filas del POS, matrices de decisión (hoy, Año 2, Año 5), ingesta híbrida y 7 diagramas interactivos. |
| **Taller 2 · Modelo dimensional** | Filtro de las 18 tarjetas hecho/dimensión, elección del grano, esquema estrella en SVG, estrella vs copo de nieve, simulador de SCD tipo 1 y 2, aditividad de métricas y respuesta a las 4 quejas. |
| **Taller 3 · Data Vault** | Capas Bronze/Silver/Gold, diagrama interactivo del Raw Vault, selector de los 3 lotes con la historia de Ana, `gold.dim_cliente` con SCD tipo 2, reportes «ciudad al comprar» vs «ciudad actual», auditoría y recomendación. |
| **Conclusiones por taller** | Una gráfica explorable por taller: puntajes por momento (T1), quejas frente a piezas del modelo (T2) y crecimiento del Vault por lote (T3). |
| **Entregables** | Enlaces a los PDF de los tres talleres y a los diagramas. |

### Navegación

- **Menú lateral en acordeón** por taller, con progreso de lectura por grupo y una barra de progreso general en la parte superior.
- **Botones «Ver»** (Todo · Historia · T1 · T2 · T3 · Fin): muestran un solo taller a la vez, con botones de anterior y siguiente taller al final. Pulsar un enlace del menú que apunta a otro taller cambia la vista automáticamente.
- **Tema claro/oscuro** (sigue al sistema y se puede cambiar a mano) y diseño adaptable a móvil con menú desplegable.

## Estructura del repositorio

| Ruta | Descripción |
|---|---|
| [index.html](index.html) | Página única con todo el contenido, estilos y scripts. |
| [diagramas/](diagramas/) | Siete diagramas HTML autocontenidos del Taller 1 (d1 a d7), incrustados con `iframe`. |
| [Taller1_RetailNova_Resuelto.pdf](Taller1_RetailNova_Resuelto.pdf) | Taller 1 resuelto. |
| [Taller2_RetailNova_Resuelto.pdf](Taller2_RetailNova_Resuelto.pdf) | Taller 2 resuelto. |
| [Taller3_RetailNova_DataVault_Resuelto.pdf](Taller3_RetailNova_DataVault_Resuelto.pdf) | Taller 3 resuelto. |
| [render.yaml](render.yaml) | Blueprint de Render (Static Site). |

## Tecnología

HTML, CSS y JavaScript puros: sin dependencias, sin build y sin servidor. Los diagramas del Taller 1 son archivos HTML independientes; los esquemas y gráficas de los talleres 2 y 3 son SVG y HTML dentro de `index.html`, y las animaciones respetan `prefers-reduced-motion`.

## Ejecutar en local

Basta con abrir `index.html` en el navegador, o servir la carpeta:

```bash
python -m http.server 8000
# luego visitar http://localhost:8000
```

## Despliegue en Render

El repositorio incluye [render.yaml](render.yaml) (Blueprint) que define un **Static Site**; no requiere build ni variables de entorno.

### Opción A — Blueprint (recomendada)
1. Subir el repositorio a GitHub, incluidos los tres PDF.
2. En [Render](https://dashboard.render.com): **New → Blueprint** y seleccionar este repositorio.
3. Confirmar el servicio `retail-nova-tecnicas-datos` y pulsar **Apply**.

### Opción B — Manual
1. **New → Static Site** y conectar el repositorio.
2. **Build Command:** *(vacío)* — **Publish Directory:** `./`
3. Pulsar **Create Static Site**.

Cada `git push` a `main` redespliega automáticamente. La página queda disponible en `https://retail-nova-tecnicas-datos.onrender.com` (o el nombre que Render asigne).

## Nota

RetailNova es una empresa ficticia creada para el curso. Los diagramas del Taller 1 se generaron con Archify.

## Licencia

Ver [LICENSE](LICENSE).
