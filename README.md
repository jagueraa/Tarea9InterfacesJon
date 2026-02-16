# Práctica: Accesibilidad Web WCAG 2.2 (WAI)

## 1. Objetivo

El objetivo de esta práctica ha sido desarrollar y validar un prompt maestro para asistentes inteligentes de programación (Copilot / Codex) capaz de transformar código HTML sin accesibilidad en código conforme a los estándares WCAG 2.2 nivel AA (AAA opcional), aplicando semántica HTML5 y atributos ARIA cuando fuese necesario.

---

## 2. Estructura del repositorio

El repositorio contiene la siguiente organización:

original/      → Archivos HTML sin accesibilidad  
accesible/     → Archivos HTML corregidos mediante el prompt  
capturas/      → Evidencias de validación antes y después  
README.md      → Documentación completa del proceso  

Archivos desarrollados:

- index-form.html
- index-table.html
- index-landing.html

Cada archivo cuenta con:
- Versión original
- Versión accesible generada mediante prompt
- Capturas de validación antes y después

---

## 3. Prompt maestro utilizado

Eres un asistente experto en Accesibilidad Web (WCAG 2.2, WAI-ARIA) y debes REESCRIBIR el HTML que pego al final para que cumpla WCAG 2.2 nivel AA (y AAA opcional si no rompe nada). El objetivo es que el HTML final no tenga errores críticos en WAVE, Axe y Lighthouse (Accessibility), y que siga buenas prácticas de accesibilidad (semántica + teclado + foco + contraste + formularios + tablas + imágenes + enlaces).

REGLAS OBLIGATORIAS:
1) Devuelve SOLO el HTML final completo corregido (un único bloque de código). No incluyas explicaciones fuera del HTML.
2) No elimines contenido ni funcionalidad; adapta y mejora para accesibilidad.
3) Usa HTML semántico primero. ARIA solo cuando sea necesario y correcto. Evita roles redundantes (no role="button" en <button>, etc.).
4) Asegura accesibilidad por teclado total: orden lógico, foco visible, sin trampas. Prohibido tabindex positivo.
5) Si hay elementos clicables que no son interactivos (div/span con onclick), conviértelos a <button> o <a> según corresponda.
6) Mejora contraste y foco visible añadiendo un <style> mínimo dentro del <head> si hace falta. Mantén diseño simple.
7) Incluye “skip link” al inicio para saltar al contenido principal.
8) Añade landmarks: <header>, <nav>, <main>, <footer> cuando proceda.
9) Corrige jerarquía de encabezados: un <h1> único y h2/h3 coherentes.
10) Formularios: cada control con <label for>, required si aplica, ayudas con aria-describedby, mensajes con aria-live cuando proceda, autocomplete si aplica.
11) Imágenes: alt descriptivo si informativas; si decorativas alt="".
12) Enlaces: texto descriptivo. Evita “click aquí”. Si abren nueva pestaña, indícalo.
13) Tablas (si existen): <caption>, <thead>, <tbody>, <th scope>, etc.
14) Añade accesskey SOLO si tiene sentido: máximo 3 y sin conflictos. Documenta en comentario HTML al inicio cuáles son.
15) Añade atributos ARIA solo si realmente aportan y están bien enlazados (aria-label, aria-labelledby, aria-describedby, aria-expanded, aria-controls, aria-live). No uses aria-hidden en elementos enfocables.
16) Asegura idioma del documento con lang="es" (salvo que el contenido esté en otro idioma).
17) Si necesitas JS mínimo para accesibilidad (solo si hay menú desplegable/modal/tabs), inclúyelo dentro de <script> y que gestione aria-* y foco correctamente. Si no hay componente dinámico, no añadas JS.

SALIDA OBLIGATORIA DENTRO DEL HTML:
- Al final del documento, incluye un bloque de comentarios HTML con:
  a) Lista de cambios realizados.
  b) Puntos que deberían mejorar en WAVE/Axe/Lighthouse.
  c) Mejoras AAA opcionales aplicadas o pendientes.

AHORA MODIFICA ESTE HTML ORIGINAL (pégalo completo a continuación):

El prompt fue diseñado para:

- Añadir semántica HTML5 (header, nav, main, section, footer).
- Corregir jerarquía de encabezados.
- Asociar correctamente etiquetas label con inputs.
- Añadir atributos ARIA cuando fuese necesario.
- Garantizar navegación por teclado y foco visible.
- Mejorar contraste y legibilidad.
- Corregir tablas mediante caption, thead, tbody y th con scope.
- Añadir textos alternativos en imágenes.
- Sustituir elementos no semánticos por botones o enlaces reales.
- Cumplir WCAG 2.2 nivel AA.

Cada archivo fue procesado mediante una única ejecución del prompt partiendo del HTML original.

---

## 4. Proceso seguido

1. Creación de varios archivos HTML sin especial atención a la accesibilidad.
2. Validación inicial con herramientas especializadas:
   - WAVE
   - Axe DevTools
3. Captura de evidencias antes de aplicar mejoras.
4. Aplicación del prompt maestro en el asistente inteligente.
5. Generación del código accesible.
6. Nueva validación con las mismas herramientas.
7. Captura de evidencias después de la corrección.
8. Documentación completa del proceso.

---

## 5. Herramientas de validación utilizadas

- WAVE (WebAIM)
- Axe DevTools (extensión de navegador)

Estas herramientas permitieron identificar:

- Falta de etiquetas asociadas a formularios
- Imágenes sin texto alternativo
- Uso incorrecto de elementos interactivos
- Problemas estructurales en tablas
- Jerarquía incorrecta de encabezados
- Falta de landmarks semánticos

---

## 6. Resultados obtenidos

### Formulario

Antes:
- Falta de etiquetas asociadas a inputs.
- Uso de elementos no semánticos como botones.
- Estructura sin landmarks.

Después:
- Estructura semántica completa.
- Labels correctamente asociados.
- Región de estado accesible.
- Foco visible y navegación por teclado.
- Mejora de contraste y legibilidad.

Nota: WAVE mostró un error relacionado con un recurso inyectado por el entorno de desarrollo (Live Server). Dicho error no corresponde al código fuente HTML del documento.

---

### Tabla

Antes:
- Uso de `<td>` en lugar de encabezados `<th>`.
- Ausencia de `<thead>`, `<tbody>` y `<caption>`.
- Campo de búsqueda sin etiqueta asociada.

Después:
- Estructura correcta de tabla con `<caption>`, `<thead>`, `<tbody>` y `<th scope>`.
- Campo de búsqueda con etiqueta asociada.
- Mejora de semántica y navegación accesible.

---

### Landing

Antes:
- Uso excesivo de `<div>` sin semántica.
- Imágenes sin atributo `alt`.
- Elementos interactivos no accesibles.
- Estructura sin landmarks.

Después:
- Uso de header, nav, main, section y footer.
- Botones reales accesibles por teclado.
- Texto alternativo en imágenes.
- Jerarquía correcta de encabezados.
- Mejora del foco visible y contraste.

---

## 7. Conclusión

El desarrollo de un prompt estructurado permite automatizar la mejora de accesibilidad web cumpliendo los criterios WCAG 2.2 nivel AA.

El proceso demuestra que los asistentes inteligentes pueden ser utilizados como herramienta de apoyo para generar código accesible, siempre que se definan instrucciones precisas y se valide el resultado mediante herramientas especializadas.

La práctica confirma la importancia de la validación técnica y la documentación del proceso para garantizar conformidad con los estándares internacionales de accesibilidad.

---