# Usability Report

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRF017nhV-TFmNER2OM8UbXtdN6xwAKBYrv0i6onNfKu6Yn0BV0RK6aiOroeXl73LSY-B0&usqp=CAU" alt="usability Download png" style="height:150px" />

### Evaluación de usabilidad del proyecto Punto Café (Caso B)

31 de mayo de 2026

### Realizado por:  
Equipo de UX/UI Asignado. Especialistas en evaluación heurística, accesibilidad web y análisis biométrico (Eye Tracking). Contamos con experiencia validando flujos de e-commerce y optimizando la tasa de conversión y la experiencia de usuario.

---

## 1. RESUMEN EJECUTIVO (Executive Summary)

- **Objetivo:** Evaluar la usabilidad, eficiencia de navegación y accesibilidad del prototipo "Punto Café" (Caso B), una cafetería de especialidad con e-commerce. Se busca identificar fricciones en el flujo de compra y compararlo frente a la propuesta alternativa (Caso A: Cyber Gourmet).
- **Metodología:** Reclutamiento de 10 usuarios (5 asignados al Caso B) para pruebas combinando A/B Testing, cuestionarios estandarizados SUS (System Usability Scale) y análisis biométrico mediante mapas de calor (Eye Tracking).
- **Principales Hallazgos:** 1. La arquitectura de la información es intuitiva y familiar para el usuario de e-commerce.
  2. La tipografía decorativa genera un alto esfuerzo cognitivo y penaliza la legibilidad.
  3. Los campos de formulario carecen de límites visuales y buen contraste, dificultando el *checkout*.
- **Resultado Global:** El sistema obtiene una puntuación media SUS de **82,5**, situándolo en la categoría de **"Aceptable (Tipo B/A)"**. Es un diseño superior en usabilidad estructural frente al Caso A (73,75), pero requiere correcciones urgentes de accesibilidad visual.

---

## 2. Metodología y Reclutamiento

- **Perfil de los participantes:** Muestra de 5 usuarios para el Caso B con edades de 20 a 59 años y experiencia TIC variable. Para el análisis profundo (SUS), destacamos a:
  - *Paula (U3):* 28 años, Arquitecta (Media exp. TIC). Perfil visual y crítico con la estética.
  - *Javier (U4):* 20 años, Estudiante (Media exp. TIC). Impulsivo y rápido navegando.
- **Escenario de la prueba:** Fases secuenciales: (1) Exploración libre y reconocimiento de marca en Landing. (2) Búsqueda de información física (locales, horarios). (3) Navegación en tienda (búsqueda y filtros). (4) Flujo de compra, configuración de producto y *checkout*.
- **Herramientas:** Simulación de GazeMapping (Eye Tracking), cuestionarios tipo Tally para SUS, y evaluación heurística basada en Lighthouse/WAVE.

---

## 3. Resultados del Cuestionario SUS (Datos Cuantitativos)

- **Comparativa A vs. B:** El Caso B (Punto Café) superó claramente en usabilidad percibida al Caso A (Cyber Gourmet). Mientras el Caso A generó cierta confusión por su complejidad, el Caso B resultó directo y predecible.
- **Desglose por ítems:** - *Fortalezas:* Los ítems sobre "facilidad de uso" y "aprendizaje rápido" rozaron la puntuación máxima.
  - *Fricciones:* El ítem sobre "complejidad innecesaria" fue puntuado ligeramente peor por los perfiles más visuales (U3), correlacionando con la dificultad de lectura de la fuente decorativa.

Valoración numérica del SUS - **82,5 / 100** (Aceptable)

---

## 4. Análisis de Eye Tracking (Datos Biométricos)

- **Heatmaps (Mapas de calor):** - *Landing Page:* Fuerte concentración en el Logo superior y en el CTA principal "Ver Productos".
  - *Tienda:* La mirada sigue un patrón clásico en "F", concentrando la atención en el primer producto del catálogo ("Pack Esencia").
  - *Producto:* Altísima atención en la imagen y el botón de retorno, aunque el CTA "Agregar al carrito" compite visualmente con los selectores de cantidad.
- **Zonas de Silencio:** El pie de página (*footer*) completo (iconos de redes sociales, newsletter) fue ignorado. La información de horarios en la landing pasó desapercibida para usuarios de navegación rápida como Javier.
- **Hallazgo clave:** La atención del usuario se dispersa en la vista de Producto al buscar los selectores (Grano/Molido); la falta de contenedores visuales claros hace que la mirada rebote antes de encontrar el botón de compra.

---

## 5. Auditoría de Accesibilidad

- **Puntuación Automática:** Estimación en Lighthouse: 65/100. WAVE: 5 Errores críticos y 4 Errores de contraste.
- **Principales barreras:**
  - *Contraste (Crítico):* Textos secundarios y *placeholders* en formularios ilegibles por falta de contraste frente al fondo.
  - *Legibilidad (Crítico):* Uso de tipografía decorativa en CTAs y menús que impide una lectura clara (perjudica a dislexia/visión reducida).
  - *Navegación (Media):* Enlaces sociales del footer sin etiquetas `aria-label` para lectores de pantalla.
  - *Estructura (Media):* Campos de entrada (inputs) marcados solo por una línea fina, lo que confunde sobre su área clicable.

---

## 6. Conclusiones y Recomendaciones (Actionable Insights)

El diseño cuenta con un modelo mental sólido, pero sus decisiones estéticas sabotean la experiencia final. 

| **Prioridad** | **Hallazgo** | **Recomendación de Mejora** |
| :--- | :--- | :--- |
| **Alta (Crítica)** | Fuente decorativa ilegible en botones (CTA) y encabezados, elevando el esfuerzo cognitivo. | Limitar la fuente decorativa al logotipo. Sustituir la tipografía de UI por una fuente *Sans-Serif* limpia. |
| **Alta (Crítica)** | Formularios con contraste deficiente y sin límites visuales claros (No pasa WCAG AA). | Oscurecer los textos (*placeholders*) y diseñar los *inputs* como cajas cerradas con bordes perimetrales. |
| **Media** | El *footer* (redes sociales y newsletter) es una zona de silencio visual y carece de accesibilidad. | Aumentar el peso visual del *footer* y añadir etiquetas `aria-label` a los iconos interactivos. |
| **Baja** | Usuarios de navegación rápida ignoran la selección obligatoria del tipo de molienda. | Añadir un borde de foco fuerte y un estado de error claro si intentan comprar sin seleccionar el grano. |
