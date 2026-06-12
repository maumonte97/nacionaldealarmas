# Documento de cambios — Nacional de Alarmas

**Periodo:** 10 al 12 de junio de 2026
**Punto de partida:** desde que se empezó a agregar el banner de la pantera (commit `d512256`) hasta el estado actual (`c7eba65`).
**Rama:** `main` (todo pusheado).

> Resumen ejecutivo: en este tramo se creó y unificó el **banner de la pantera** en todas las secciones, se hizo una pasada completa de **adaptación a móvil** (navbar, footer, carrusel, catálogos, contadores, imágenes) y se mejoró el **rendimiento**. Todos los cambios están guardados en el repositorio.

---

## 1. Banner de la pantera (el cambio principal)

Evolución del banner desde su creación hasta su versión final unificada:

- **Creación e integración (cámaras).** Se agregó el banner de la pantera sin texto antes del footer y se fue integrando con el fondo: ajuste de tamaño, anclaje, márgenes para no cortar la boca/orejas y conservar el degradado. (`d512256`, `0b53036`, `7c2b950`, `ce46c3a`, `ebd6523`, `e529fc4`, `01e8bfc`, `5810e4f`, `afb889d`)
- **Unificación.** Se unificó el mismo banner en industrial y comercial, y luego en **todas** las secciones que lo llevan (comercial, industrial, cámaras, servicios, nosotros). (`377bba1`, `5a250d0`, `54981f8`, `6e2c59d`, `741f8d4`)
- **Adaptación a móvil.** Pantera completa y más compacta (modo `contain`), banner más chico, degradado que funde la pantera con el fondo (negro al centro, azul al borde), control del amarillo. (`2463872`, `1cf0ca3`, `fc93b89`, `fe86a8f`, `fc01d6a`)
- **Slogan.** Se reemplazó el contenido por el slogan **"Resuelve tu seguridad en nuestras manos"**, sin botones:
  - Solo la "R" en mayúscula, el resto en minúsculas. (`09915f7`)
  - Paleta solo negro y azul (se quitó el glow amarillo). (`741de33`)
  - **"seguridad"** y **"manos"** en amarillo. (`599958c`)
  - En móvil, frase en 3 líneas: *Resuelve tu / seguridad en / nuestras manos*. (`599958c`, `09b1eb2`)
  - El **ojo de la pantera colorido** (se quitó el filtro de saturación que lo opacaba). (`13a1e7b`)
- **Versión web (escritorio) — ajustes finales.** Frase **centrada** y con aire del borde derecho, y se **agrandó** progresivamente la tipografía (34 → 46 → 54 px), manteniendo el resaltado amarillo en "seguridad" y "manos". (`29e0eb0`, `8f4a8cc`, `c7eba65`)

---

## 2. Footer en móvil

- Footer **centrado en todas las páginas** (logo, texto, redes sociales, columnas y copyright). (`d2dbbec`)
- Corrección del **corrimiento a la derecha**: el logo se renderizaba demasiado ancho (~415 px) y desbordaba, empujando las columnas. (`445a023`)
- Ajuste final: **logo a su tamaño original, centrado**, sin mover el texto (se fijó el ancho de la columna con `minmax(0,1fr)` y se centró el logo por flex). (`6fee878`)

---

## 3. Navbar en móvil

- **Pop-up de pilares** y **dropdown** del navbar arreglados en home. (`82c1be7`)
- En iOS, al cerrar el menú **ya no se cancela la navegación**. (`6fe6604`)
- Se **portaron las correcciones de home a todas las páginas** (navbar consistente y funcional). (`ff15f1b`, `5f155df`)
- El botón **hamburguesa ya no se sale** al hacer scroll. (`35fe051`)

---

## 4. Rendimiento

- **Lazy-load** de imágenes y se quitó una regla GPU global que afectaba el render. (`e2f51d4`)
- **Compresión de imágenes** (pngquant + JPEG calidad 72). (`025e1e3`)
- Iconos **Phosphor cargados por CSS** en vez de `<script>` bloqueante (carga más rápida). (`5b0c445`)

---

## 5. Carrusel y catálogo (comercial)

- Se ocultó la **onda del hero** y se reposicionaron las imágenes del catálogo. (`75ebfb6`)
- Reencuadres de las imágenes del catálogo **solo en móvil** (escritorio queda con su encuadre original). (`96f9a03`)
- Ajustes finos de encuadre por imagen para que se vea el sensor: contacto magnético, apertura, área general (PIR), exterior. (`f74984e`, `a3c2dcb`, `112d3e0`, `c424713`, `7396ce1`, `9c13c99`, `f82cff1`, `3299305`, `54aae0f`, `b58a080`)
- **Carrusel del hero (móvil):** se alinearon los iconos de los badges (Oficinas/Colegios — el icono ya no queda en medio de la palabra), más espacio entre el badge y los dots. (`3da7a66`, `487bff3`)
- **Paquetes (móvil):** se acomodó el botón "Más información a tu medida" para que no quede "medida" separada. (`30640bb`)

---

## 6. Ajustes por página (móvil)

**Residencial**
- Collage de polaroids rotado y traslapado; en 2 filas de 3 fotos; rotación de imágenes cada 10 s. (`978be29`, `b9e471e`, `f8df0db`)
- Tabs de "Vista rápida" compactos (una sola línea, luego en 2×2 igual a comercial/industrial). (`cad0131`, `8b9a8be`)
- Imagen de contacto cableado alineada a la izquierda; PIR reposicionado y auto-cambio más lento. (`407f11f`, `99bf10b`)

**Industrial**
- Se muestra la imagen del hero (estaba oculta) y se quitó el radar. (`f09c365`)
- Ajuste de la imagen de Perimetral; interior muestra el sensor PIR; pantera adaptada igual que comercial. (`8c22bff`, `df3f8ff`, `6e2c59d`)

**Nosotros**
- Se corrigió el **temblor del contador** del hero y se **centró**. (`ab034de`, `a4655e1`)
- Se muestra la imagen en "Una trayectoria" (logo del ojo, adaptada de web). (`fb19008`, `b6f40a8`)
- Se subió la imagen de misión para quitar el hueco. (`76a7adb`)

**Servicios**
- Pantera visible detrás del texto del banner. (`54981f8`)

---

## Listado cronológico completo de commits

| Fecha | Commit | Descripción |
|---|---|---|
| 2026-06-10 | `d512256` | Cámaras: agrega banner de la pantera (sin texto) antes del footer |
| 2026-06-10 | `0b53036` | Cámaras: integra el banner de la pantera con el fondo |
| 2026-06-10 | `7c2b950` | Cámaras: ajusta el banner de la pantera (grande, anclada arriba, integrada) |
| 2026-06-10 | `ce46c3a` | Cámaras: revierte el banner de la pantera a la versión original |
| 2026-06-10 | `ebd6523` | Cámaras: muestra la pantera completa manteniendo el degradado |
| 2026-06-10 | `e529fc4` | Cámaras: deja margen en el banner para no cortar la boca de la pantera |
| 2026-06-10 | `01e8bfc` | Cámaras: usa el banner de la pantera de servicios |
| 2026-06-10 | `5810e4f` | Cámaras: banner de la pantera sin texto (estilo servicios) |
| 2026-06-10 | `afb889d` | Cámaras: agranda un poco el banner de la pantera (min-height 380px) |
| 2026-06-10 | `377bba1` | Unifica el banner de la pantera en industrial y comercial |
| 2026-06-10 | `82c1be7` | Home móvil: arregla pop-up de pilares y dropdown del navbar |
| 2026-06-10 | `6fe6604` | Home navbar móvil: no cancelar la navegación en iOS al cerrar el menú |
| 2026-06-10 | `e2f51d4` | Rendimiento móvil: lazy-load de imágenes y quita regla GPU global |
| 2026-06-10 | `025e1e3` | Rendimiento: comprime imágenes (pngquant + jpeg q72) |
| 2026-06-10 | `978be29` | Residencial móvil: collage de polaroids rotado y traslapado |
| 2026-06-10 | `b9e471e` | Residencial móvil: collage en 2 filas de 3 fotos más chicas |
| 2026-06-10 | `f8df0db` | Residencial móvil: collage un poco más grande y rota imágenes cada 10s |
| 2026-06-10 | `cad0131` | Residencial móvil: tabs de Vista rápida chicos y en una sola línea |
| 2026-06-11 | `407f11f` | Residencial: alinea a la izquierda la imagen de contacto cableado |
| 2026-06-11 | `99bf10b` | Residencial: reposiciona PIR (sensor visible) y ralentiza el auto-cambio |
| 2026-06-11 | `ff15f1b` | Navbar móvil: porta las correcciones de home a todas las páginas |
| 2026-06-11 | `5b0c445` | Rendimiento: iconos Phosphor por CSS en vez de `<script>` bloqueante |
| 2026-06-11 | `75ebfb6` | Comercial: oculta onda del hero y reposiciona imágenes del catálogo |
| 2026-06-11 | `f74984e` | Comercial: puerta de negocio (overhead) de apertura a la izquierda |
| 2026-06-11 | `96f9a03` | Catálogo: reencuadres de imágenes solo en móvil |
| 2026-06-11 | `a3c2dcb` | Comercial: revierte encuadre de contacto magnético en apertura |
| 2026-06-11 | `112d3e0` | Comercial móvil: contacto magnético (apertura) un poco a la izquierda (40%) |
| 2026-06-11 | `c424713` | Comercial móvil: contacto magnético más a la izquierda (15%) |
| 2026-06-11 | `7396ce1` | Comercial móvil: contacto magnético a la derecha (right bottom) para mostrar el sensor |
| 2026-06-11 | `9c13c99` | Comercial móvil: área general muestra el sensor PIR (object-position left) |
| 2026-06-11 | `f82cff1` | Comercial móvil: exterior un poco más a la derecha (85%) |
| 2026-06-11 | `3299305` | Comercial móvil: exterior a la derecha (right). Solo móvil; escritorio centrado. |
| 2026-06-11 | `54aae0f` | Comercial móvil: exterior a la izquierda (25%) |
| 2026-06-11 | `b58a080` | Comercial móvil: exterior un poco más a la izquierda (10%) |
| 2026-06-11 | `2463872` | Comercial móvil: pantera completa y más chica en el banner (contain) |
| 2026-06-11 | `1cf0ca3` | Comercial móvil: banner de la pantera más chico (220px) |
| 2026-06-11 | `fc93b89` | Comercial móvil: pantera se funde con el degradado (sin corte) y termina en azul |
| 2026-06-11 | `fe86a8f` | Comercial móvil: degradado de la pantera más negro (azul solo al borde) |
| 2026-06-11 | `fc01d6a` | Comercial móvil: reduce el amarillo de la pantera (filter saturate 0.5) |
| 2026-06-11 | `f09c365` | Industrial móvil: muestra la imagen del hero (estaba oculta) y quita el radar |
| 2026-06-11 | `8c22bff` | Industrial móvil: baja un poco la imagen de Perimetral (center 25%) |
| 2026-06-11 | `df3f8ff` | Industrial móvil: interior muestra el sensor PIR (object-position right) |
| 2026-06-11 | `6e2c59d` | Industrial móvil: pantera adaptada igual que comercial |
| 2026-06-11 | `8b9a8be` | Residencial móvil: tabs de Vista rápida en 2x2 (igual a comercial/industrial) |
| 2026-06-11 | `54981f8` | Servicios móvil: pantera visible detrás del texto del banner |
| 2026-06-11 | `ab034de` | Nosotros móvil: corrige el temblor del contador del hero |
| 2026-06-11 | `a4655e1` | Nosotros móvil: centra el contador del hero |
| 2026-06-11 | `fb19008` | Nosotros móvil: muestra la imagen en la sección "Una trayectoria" |
| 2026-06-11 | `b6f40a8` | Nosotros móvil: usa la imagen de web (logo del ojo) en "Una trayectoria" |
| 2026-06-11 | `76a7adb` | Nosotros móvil: sube la imagen de misión (sin hueco) |
| 2026-06-11 | `5a250d0` | Nosotros: banner de la pantera igual a comercial (sin texto) |
| 2026-06-11 | `35fe051` | Navbar móvil: el hamburguesa ya no se sale al hacer scroll |
| 2026-06-11 | `5f155df` | Navbar móvil consistente: arregla camaras (logo) y privacidad (JS) |
| 2026-06-12 | `741f8d4` | Banner pantera unificado en todas: slogan sin botones |
| 2026-06-12 | `09915f7` | Banner pantera: slogan en minúsculas (solo R mayúscula) |
| 2026-06-12 | `741de33` | Banner pantera: quita el amarillo (oculta glow-yellow + baja saturación) |
| 2026-06-12 | `599958c` | Banner pantera: slogan 3 líneas en móvil con "seguridad" y "manos" en amarillo |
| 2026-06-12 | `d2dbbec` | Footer móvil centrado en todas las páginas |
| 2026-06-12 | `09b1eb2` | Banner móvil: saltos del slogan (Resuelve tu / seguridad en / nuestras manos) |
| 2026-06-12 | `13a1e7b` | Banner pantera: ojo colorido (quita filtro de saturación) |
| 2026-06-12 | `445a023` | Fix: centrar footer en móvil (constreñir ancho del logo que desbordaba) |
| 2026-06-12 | `6fee878` | Footer móvil: logo a tamaño original centrado sin mover el texto |
| 2026-06-12 | `3da7a66` | Carrusel hero comercial: alinear iconos de los badges (colegios/oficinas) |
| 2026-06-12 | `487bff3` | Carrusel hero comercial: más espacio entre el badge y los dots en móvil |
| 2026-06-12 | `30640bb` | Paquetes comercial: acomodar botón 'Más información a tu medida' en móvil |
| 2026-06-12 | `29e0eb0` | Banner pantera (web): centrar la frase y darle aire del borde derecho |
| 2026-06-12 | `8f4a8cc` | Banner pantera (web): frase más grande (34px → 46px) |
| 2026-06-12 | `c7eba65` | Banner pantera (web): frase un poco más grande (46px → 54px) |

---

*Documento generado el 12 de junio de 2026. Todos los cambios listados están commiteados y pusheados en la rama `main`.*
