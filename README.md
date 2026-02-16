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

(Pegar aquí el prompt final exacto utilizado en Copilot/Codex)

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
   - Lighthouse
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
- Lighthouse (integrado en Chrome DevTools)

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

## English Version

### Objective

The objective of this assignment was to develop and validate a master prompt capable of transforming non-accessible HTML into WCAG 2.2 AA compliant code using semantic HTML5 and ARIA attributes when required.

### Process

1. Creation of multiple non-accessible HTML files.
2. Initial validation using WAVE, Axe DevTools and Lighthouse.
3. Application of a single master prompt per file.
4. Generation of accessible versions.
5. Re-validation and documentation.

### Final Result

The accessible versions comply with WCAG 2.2 AA requirements.  
Validation tools confirm structural, semantic and accessibility improvements.
