# Rueda Libre

Sitio web de **Rueda Libre**, un negocio de alquiler de bicicletas y recorridos guiados. Muestra los servicios, las tarifas, los recorridos y un formulario de reservas, para reemplazar las reservas por WhatsApp, que generaban errores de fechas, datos incompletos y bicicletas no disponibles.

Proyecto de práctica del entrenamiento de programación de Riwi (HTML, CSS y GitHub). Autor: Edil.

**Sitio publicado:** https://edilbertojusayu20.github.io/Rueda_libre_def/

---

## Páginas

| Página | Archivo | Qué contiene |
|---|---|---|
| Inicio | `index.html` | Quiénes somos, servicios en tarjetas, cómo alquilar, beneficios y ubicación |
| Tarifas y rutas | `paginas/tarifas.html` | Tabla de tarifas de alquiler, tabla de recorridos guiados e información adicional |
| Reservas | `paginas/reservas.html` | Formulario de reserva con validación y horario de atención |

## Estructura del proyecto

```
├── index.html
├── css/
│   └── styles.css
├── img/
│   ├── portada.jpg
│   ├── bicicleta.jpg
│   ├── ruta.jpg
│   └── logo.png
├── paginas/
│   ├── tarifas.html
│   └── reservas.html
├── bitacora/
│   └── bitacora-minireto-*.md
└── README.md
```

## Tecnologías

- HTML5 semántico
- CSS3 con variables, sin estilos en línea ni `!important`
- Google Fonts: Montserrat (700) para títulos y Open Sans (400 y 600) para textos
- Git y GitHub Pages

No usa JavaScript ni librerías externas. Para verlo en local basta abrir `index.html` en el navegador.

---

## Cómo se construyó, paso a paso

Cada etapa corresponde a un MiniReto del entrenamiento y a un commit.

| MiniReto | Tema | Qué se hizo |
|---|---|---|
| 3 | Estructura de la página de inicio | Un solo `h1`, secciones con `h2` y servicios con `h3`; párrafos con `<strong>` y `<em>`; lista numerada con los 4 pasos para alquilar y lista con viñetas con 3 beneficios; 3 imágenes con ruta relativa, `alt` y `width`; 3 tipos de enlace (externo con `target="_blank"`, `mailto:` e interno con `#id`) |
| 4 | Tablas y rutas entre carpetas | `paginas/tarifas.html` con dos tablas accesibles (`caption`, `thead`, `tbody`, `th` con `scope`); información adicional en párrafos y lista; enlaces en ambos sentidos entre inicio y tarifas con `../` y con `archivo#id` |
| 5 | Sitio navegable | Página `paginas/reservas.html` con lista de definiciones para el horario; menú común (`<nav>` con `<ul>`) y pie de página en las tres páginas; enlaces "Reservar ahora"; tabla de rutas relativas desde cada archivo |
| 6 | Formulario | Formulario `post` con 3 grupos (`fieldset` y `legend`): Tus datos, Tu alquiler y Confirmación; cada dato con el control adecuado (`text`, `email`, `tel`, `date`, `number`, `radio`, `select`, `textarea`, `checkbox`); `label` con `for` y `name` en todos los controles |
| 7 | Validación nativa | Reglas del cliente traducidas a atributos (`required`, `minlength`, `maxlength`, `pattern`, `min`, `max`); navegación completa con teclado |
| 8 | Accesibilidad y contraste | Auditoría de las tres páginas (enlace para saltar al contenido, `aria-current`, `<main>`, textos de ayuda, `autocomplete`); contraste de la paleta de marca y mapa de uso de color; publicación en GitHub Pages |
| 9 | Hoja de estilos y tipografías | `css/styles.css` enlazado en las tres páginas; Google Fonts; variables de color, tipografía y espaciado; herencia desde `body` |
| 10 | Navegación, enlaces y botones | Clase `activo` e `id="menu"`; conflicto de especificidad resuelto; estados `:hover` y `:focus` visibles en menú, enlaces, botones y campos |
| 11 | Modelo de caja | `box-sizing: border-box` global; contenedor con `max-width` en `rem` y centrado; servicios en tarjetas; tablas y formulario con relleno y separación en `rem`; menú en fila con `inline-block` |
| 12 | 	Etiqueta "Nuevo", WhatsApp fijo, consistencia entre páginas y CSS organizado.

La bitácora de los MiniRetos 8 al 11 está en la carpeta [`bitacora/`](bitacora/).

---

## Decisiones de diseño

### Paleta de marca y contraste

| Color | Código | Uso |
|---|---|---|
| Verde Ruta | `#1E7A4F` | Botones y enlaces |
| Naranja Pedal | `#F39A2B` | Destacados y fondo de hover del menú |
| Azul Noche | `#14213D` | Títulos y texto principal |
| Crema | `#FAF6EF` | Fondo general |
| Gris Asfalto | `#5B6470` | Texto secundario |
| Blanco | `#FFFFFF` | Texto sobre Verde Ruta y Azul Noche, fondo de tarjetas y campos |

Relaciones de contraste calculadas con la fórmula WCAG (mínimo 4.5:1 para texto normal):

| Combinación | Relación | Resultado |
|---|---|---|
| Azul Noche sobre Crema | 14.83:1 | Apta |
| Gris Asfalto sobre Crema | 5.57:1 | Apta |
| Verde Ruta sobre Crema | 4.93:1 | Apta |
| Blanco sobre Verde Ruta | 5.31:1 | Apta |
| Blanco sobre Azul Noche | 15.97:1 | Apta |
| Azul Noche sobre Naranja Pedal | 7.20:1 | Apta |
| Blanco sobre Naranja Pedal | 2.22:1 | **No apta** |
| Naranja Pedal sobre Crema | 2.06:1 | **No apta** |

**Regla:** el Naranja Pedal nunca se usa como color de texto; solo como fondo con texto Azul Noche.

### Accesibilidad

- Un solo `h1` por página y jerarquía de encabezados sin saltos.
- Todas las imágenes tienen `alt` y las tablas tienen `caption` y `th` con `scope`.
- Cada campo tiene su `label`, y el formato esperado se explica con texto visible.
- Enlace "Saltar al contenido" y `aria-current="page"` en el menú.
- Indicador de foco visible en todos los elementos interactivos.
- `lang="es"` en las tres páginas.

### Reglas de validación del formulario

| Campo | Regla |
|---|---|
| Nombre completo | Obligatorio, mínimo 3 caracteres |
| Documento | Obligatorio, solo números, entre 6 y 10 dígitos |
| Correo | Obligatorio, con formato de correo válido |
| Celular | Obligatorio, 10 dígitos y empieza por 3 |
| Fecha del alquiler | Obligatoria, entre el 1 de noviembre y el 31 de diciembre de 2026 |
| Tipo de bicicleta y plan | Obligatorios |
| Cantidad de bicicletas | Obligatoria, entre 1 y 6 |
| Comentarios | Opcional, máximo 300 caracteres |
| Políticas de alquiler | Es obligatorio aceptarlas |

### Rutas relativas entre páginas

| Desde | Hacia | Ruta escrita |
|---|---|---|
| `index.html` | Tarifas | `paginas/tarifas.html` |
| `index.html` | Reservas | `paginas/reservas.html` |
| `index.html` | Hoja de estilos | `css/styles.css` |
| `paginas/*.html` | Inicio | `../index.html` |
| `paginas/*.html` | Hoja de estilos | `../css/styles.css` |
| `paginas/tarifas.html` | Reservas | `reservas.html` |
| `paginas/reservas.html` | Tarifas | `tarifas.html` |
