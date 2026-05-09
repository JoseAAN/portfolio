Documento Justificativo: Proyecto Integrador (UT5)
Web Personal Profesional - Portfolio Digital
Alumno: José Antonio Alonso Navarro

1. Planificación del diseño (Estructura y Organización)
El portfolio se ha concebido como una Single Page Application (SPA) estática, orientada a presentar mi perfil profesional en el sector tecnológico. La arquitectura de la información se divide en cuatro bloques semánticos principales:

Hero (<header> y sección inicial): Presentación directa con propuesta de valor y llamadas a la acción (CTAs) para descargar el CV o ver proyectos.

Sobre mí: Biografía estructurada en un diseño asimétrico que separa visualmente el texto del avatar, facilitando la lectura en forma de "F".

Proyectos: Diseño basado en el patrón visual Bento Grid, que permite mostrar tarjetas de proyectos de forma modular y ordenada.

Footer: Información de contacto directa y enlaces a redes profesionales.

A nivel de código, se ha priorizado el uso de HTML5 Semántico (<main>, <section>, <article>, <nav>), abandonando el uso excesivo de <div> genéricos para dotar de significado estructural a la página.

2. Coherencia y Homogeneidad Visual
Para garantizar la consistencia en todo el sitio web, se ha implementado un sistema de diseño mediante Variables CSS (Custom Properties) en la pseudo-clase :root.

Estética "Dark Mode Minimalista": Se ha elegido una paleta oscura (fondo #0a0a0a y tarjetas #161616) que reduce la fatiga visual, transmite profesionalidad y hace destacar los colores de las tecnologías.

Tipografía: Se ha utilizado la fuente Inter (sans-serif), estándar en la industria tecnológica, garantizando máxima legibilidad en pantallas de cualquier resolución.

Armonía espacial: Se ha mantenido un sistema de espaciados coherente (uso de rem y gap) para asegurar que todos los elementos "respiren" de la misma forma.

3. Aplicación de Estilos y Maquetación
El proyecto se ha desarrollado utilizando CSS Vanilla (sin frameworks como Bootstrap o Tailwind) para demostrar un dominio real de la maquetación moderna:

CSS Grid: Aplicado magistralmente en la sección de proyectos (grid-template-columns: repeat(auto-fit, minmax(300px, 1fr))), logrando que la cuadrícula sea responsive de forma automática sin necesidad de abusar de Media Queries. También se usa en "Sobre mí" (1fr 130px) para controlar la distribución exacta entre texto e imagen en escritorio.

Flexbox: Utilizado para la alineación unidireccional, como la barra de navegación, las etiquetas de tecnologías (.tech-stack) y los elementos del pie de página.

Diseño Responsive (Mobile First): Mediante @media (max-width: 768px), la estructura muta de manera fluida. Por ejemplo, en la sección biográfica, se utiliza la propiedad order: -1 de Flexbox para forzar visualmente al avatar a situarse por encima del texto en pantallas pequeñas, sin alterar el orden lógico del DOM.

4. Preparación e Integración Multimedia
El tratamiento de los elementos gráficos se ha optimizado para el rendimiento y la estética:

Imágenes fluidas: Se ha aplicado object-fit: contain combinado con max-width: 100% en las capturas de los proyectos. Esto asegura que la imagen se adapte al contenedor sin deformarse ni recortar información valiosa de la interfaz de la captura.

Vectorial (Inline SVGs): Para los iconos de tecnologías (Laravel, Vue, AWS, etc.) y redes sociales se han utilizado archivos SVG incrustados directamente en el HTML. Esto evita peticiones HTTP adicionales (mejorando el tiempo de carga), permite escalabilidad infinita sin pérdida de calidad y facilita el cambio de colores y tamaños mediante CSS.

Efectos visuales: Se ha aplicado un filtro en escala de grises al avatar (filter: grayscale(20%)) que transiciona a todo color mediante el evento :hover, integrándolo mejor en el tema oscuro.

5. Accesibilidad (A11y)
Se han implementado prácticas recomendadas por la W3C para asegurar que la web sea navegable por cualquier usuario:

Lectores de pantalla: Todas las imágenes cuentan con su atributo alt descriptivo. Los enlaces que solo contienen iconos (como GitHub o LinkedIn en el footer) incluyen el atributo aria-label para describir su destino.

Navegación por teclado: Se ha definido un estado :focus-visible personalizado con un contorno del color de acento (outline: 2px solid var(--accent-color)) para que los usuarios que navegan mediante tabulador sepan exactamente dónde se encuentran.

Reducción de movimiento: Se ha añadido una media query @media (prefers-reduced-motion: reduce) que desactiva las transiciones y el desplazamiento suave (scroll-behavior: auto) para usuarios con sensibilidad al movimiento configurada en su sistema operativo.

Accesibilidad dinámica: El menú hamburguesa de la versión móvil actualiza su estado aria-expanded (true/false) mediante JavaScript al abrirse o cerrarse.

6. Usabilidad (UX)
La experiencia de usuario se ha cuidado mediante micro-interacciones y facilidades de navegación:

Feedback visual: Elementos interactivos como tarjetas y botones incluyen transformaciones suaves (transform: translateY(-5px) o scale(1.2) en iconos) al pasar el cursor, indicando claramente que son clickeables.

Superficie de clic (Fitts's Law): En lugar de poner un pequeño enlace de "Ver proyecto", se ha envuelto toda la tarjeta del <article> dentro de una etiqueta <a>, maximizando el área pulsable.

Navegación constante: La cabecera utiliza position: sticky con un efecto Glassmorphism (backdrop-filter: blur(12px)), permitiendo al usuario acceder al menú en cualquier punto del scroll sin perder el contexto del contenido que hay debajo.

UX Móvil: El menú hamburguesa programado en JavaScript se cierra automáticamente cuando el usuario selecciona una sección, evitando que tape el contenido al que acaba de navegar.
