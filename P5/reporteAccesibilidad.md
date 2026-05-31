# Reporte de Accesibilidad: Punto Café

<img src="https://img.uxcel.com/cdn-cgi/image/format=auto/practices/wcag-principles-overview-1742315821212/a-1742315821212-2x.jpg" alt="usability Download png" style="height:200px" />

## 1. Ficha Técnica del Informe

- **Nombre del proyecto:** Prototipos de UI - Aplicación/Web Punto Café.
- **Normativa de referencia:** WCAG 2.1 (Nivel AA).
- **Herramientas utilizadas:** Revisión heurística visual de componentes (simulación sobre mockups).
- **Fecha de la auditoría:** 31 de mayo de 2026.

---

## 2. Puntuaciones Globales (Métricas Automáticas Estimadas)

*(Nota: Al ser una evaluación sobre imágenes estáticas, estas métricas representan una estimación de lo que arrojarían las herramientas).*

- **Lighthouse Accessibility Score:** 65/100.
- **WAVE Summary:** 5 Errores críticos, 12 Alertas, 4 Errores de contraste.

---

## 3. Análisis por Principios (POUR)

<img src="https://cdn.sanity.io/images/r115idoc/production/e745ae232e5e6760c1392354021aed4eecc4627d-1920x1080.png" alt="usability Download png" style="height:200px" />

### A. Perceptible
- **Error detectado:** Falta de contraste en los textos descriptivos y de relleno (placeholders). En las pantallas de *Perfil* y *Direcciones*, los textos como "Escribe tu nombre" tienen un color gris claro sobre un fondo tenue.
- **Criterio WCAG incumplido:** Criterio 1.4.3 - Contraste mínimo.
- **Impacto:** Los usuarios con visión reducida o daltonismo tendrán graves dificultades para leer los formularios.
- **Recomendación de mejora:** Aumentar la opacidad y oscuridad del texto descriptivo para alcanzar un ratio de contraste mínimo de 4.5:1.

### B. Operable
- **Error detectado:** Enlaces a redes sociales y controles sin etiquetas visibles. Aparecen iconos de Instagram, Facebook y TikTok sin texto acompañante.
- **Criterio WCAG incumplido:** Criterio 2.4.4 - Propósito de los enlaces en su contexto.
- **Impacto:** Los usuarios que utilizan lectores de pantalla no sabrán hacia dónde dirigen estos botones.
- **Recomendación de mejora:** Asegurar la inclusión de atributos `aria-label` descriptivos en el código HTML de dichos iconos.

### C. Comprensible
- **Error detectado:** Uso generalizado de tipografía decorativa en títulos, cabeceras y botones ("Punto Café", "Volver a Tienda").
- **Criterio WCAG incumplido:** Criterio 1.4.8 - Presentación visual y legibilidad.
- **Impacto:** Dificulta severamente la lectura para usuarios con dislexia, deficiencias cognitivas o problemas de visión. El esfuerzo cognitivo es muy alto.
- **Recomendación de mejora:** Reemplazar la fuente decorativa en elementos interactivos por una fuente Sans-Serif limpia, clara y de trazo uniforme.

### D. Robusto
- **Error detectado:** Estructura visual de formularios basada únicamente en una línea inferior sin delimitar claramente su área clicable interactiva.
- **Criterio WCAG incumplido:** Criterio 3.3.2 - Etiquetas o instrucciones.
- **Impacto:** Personas con movilidad reducida pueden tener dificultades para identificar los límites del área interactiva para hacer clic o tocar con el dedo.
- **Recomendación de mejora:** Definir bordes claros (cajas completas) para los inputs y vincular explícitamente el texto superior con su campo mediante `<label>`.

---

## 4. Tabla de Hallazgos y Prioridades

| **ID** | **Prioridad** | **Criterio WCAG** | **Error detectado** | **Recomendación Técnica** |
| :--- | :--- | :--- | :--- | :--- |
| **ACC-01** | **Crítica** | 3.1.5 Legibilidad | Fuente decorativa ilegible en botones y encabezados de navegación. | Sustituir por una fuente geométrica o Sans-Serif sólida. |
| **ACC-02** | **Alta** | 1.4.3 Contraste | Formularios: Textos secundarios en gris tenue sobre fondos claros. | Oscurecer los textos a un gris oscuro (ej. #555555). |
| **ACC-03** | **Media** | 1.1.1 Contenido no textual | Iconos de redes sociales carecen de texto o etiquetas. | Aplicar `aria-label` explicativos a los iconos. |
| **ACC-04** | **Media** | 3.3.2 Etiquetas | Área de impacto visual de los inputs confusa (solo línea inferior). | Diseñar los inputs como cajas (boxes) con bordes visibles. |

---

## 5. Conclusiones y Declaración de Conformidad

- **¿Es el sitio accesible?** En su estado de diseño actual, **el sitio NO cumple con el nivel AA**. Presenta barreras críticas de usabilidad visual motivadas principalmente por una elección tipográfica altamente decorativa y contrastes insuficientes en los formularios.
- **Próximos pasos (3 acciones inmediatas):**
  1. Mantener la fuente decorativa únicamente para el logo y rediseñar los textos de la interfaz con fuentes estándar.
  2. Revisar la paleta de colores de los formularios, subiendo el contraste de las etiquetas e inputs.
  3. Asegurar que los iconos interactivos (menú, redes sociales, carruseles) integren los atributos ARIA correspondientes.
