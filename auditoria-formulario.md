# Auditoría de mejora del formulario HTML

Fecha: 2026-09-08

## Alcance
- Archivo revisado: `index.html`
- Hoja de estilos revisada: `styles.css`
- Tipo de proyecto: página estática, sin backend ni validación dinámica

## Enfoque de la auditoría
Esta auditoría está enfocada en buscar lo que le puede faltar al formulario y en detectar oportunidades de mejora para que funcione mejor en una práctica real. La idea no es decir que está mal, sino encontrar aspectos que podrían mejorarse.

## Puntos altos

### 1) Tiene una base sólida en HTML
- El formulario usa una estructura correcta con `form`, `fieldset`, `legend`, `label`, `input`, `select`, `textarea` y `button`.
- Esto ya da una buena base para un formulario limpio y comprensible.
- La organización visual y semántica ayuda bastante al usuario y a la accesibilidad.

### 2) Tiene accesibilidad básica bien llevada
- Existe una descripción general del formulario con `aria-describedby`.
- Los grupos de radios están bien etiquetados con `role="radiogroup"` y `aria-labelledby`.
- Los controles tienen foco visible, que es un punto importante para usuarios que navegan con teclado.

### 3) El diseño se ve ordenado y responsivo
- La hoja de estilos está bien organizada.
- El formulario responde adecuadamente en pantallas pequeñas.
- La apariencia visual es clara y profesional.

### 4) Hace buen uso de tipos de input
- Se aprovechan inputs especiales como `email`, `tel`, `url`, `date`, `month`, `week`, `time`, `datetime-local`, `number`, `color`, `range` y `file`.
- Esto mejora la experiencia de entrada y ayuda con validación del navegador.

## Puntos medios

### 1) Faltan mensajes claros de error
- El formulario usa `required`, pero no muestra una retroalimentación útil cuando el usuario llena algo incorrectamente.
- Eso deja un hueco importante en la experiencia, porque el usuario puede no saber qué está mal y por qué.

### 2) Algunos campos necesitan más orientación
- Campos como `month`, `week`, `datetime-local`, `range`, `color` y `file` pueden resultar poco intuitivos si no tienen instrucciones adicionales.
- En una página estática, esto puede causar confusión si el usuario no sabe exactamente qué se espera.

### 3) La contraseña no tiene reforzamiento adicional
- El campo de `password` existe, pero no hay una confirmación ni información que ayude al usuario a crear una contraseña segura.
- En un formulario de inscripción, esto suele ser un detalle importante para mejorar la confianza del proceso.

### 4) No existe un salto automático al siguiente campo con Enter
- El formulario no cambia de campo al presionar Enter.
- En HTML/CSS puro, eso no puede hacerse de forma real ni nativa: la navegación esperada es con Tab.
- Como mejora parcial, sí se puede usar `enterkeyhint="next"` para orientar el teclado virtual en dispositivos móviles.

## Puntos bajos

### 1) El campo de archivo no explica sus restricciones
- El input de tipo `file` acepta ciertos formatos, pero no informa ni tamaño máximo ni instrucciones útiles para subir el documento.
- Eso puede provocar errores comunes en el momento de enviar.

### 2) El `textarea` no tiene límite de caracteres
- El campo de intereses puede aceptar texto ilimitado.
- Esto puede ser útil para flexibilidad, pero en muchos casos conviene limitarlo para guiar mejor la respuesta del usuario.

### 3) El campo de rango no comunica el valor actual de forma clara
- El `range` tiene una escala visual, pero no muestra de manera evidente el valor actual seleccionado.
- Esto puede hacer que el usuario no sepa exactamente cuánto está eligiendo.

### 4) El comportamiento de Enter no está resuelto de forma nativa
- Aunque el formulario tiene buena estructura y accesibilidad básica, no cumple la expectativa de pasar automáticamente al siguiente campo cuando se pulsa Enter.
- Eso debe documentarse como una limitación del enfoque HTML/CSS puro.

## Recomendaciones de mejora

1. Agregar mensajes de error por campo.
2. Incluir ayuda más específica para campos complejos.
4. Añadir instrucciones para subir archivos.
5. Mejorar el flujo de validación y confirmación del formulario.
6. Definir un límite de caracteres en el `textarea` si se desea controlar la longitud de la respuesta.
7. Reforzar la accesibilidad de elementos interactivos como `range` y `file`.
8. Usar `enterkeyhint="next"` como mejora parcial y dejar claro que el salto real de foco con Enter requiere JavaScript.

## Conclusión
El formulario ya tiene una muy buena base: está bien estructurado, es visualmente limpio, es responsive y usa buenas prácticas de HTML. Sin embargo, para una auditoría enfocada en mejora, los aspectos que más le faltan son claridad de validación, mejor feedback al usuario, instrucciones adicionales en campos complejos y reforzamiento del flujo de confirmación y envío.

## Resultado final
- Estado general: Bueno, pero con varias oportunidades de mejora
- Mayor riesgo: falta de mensajes claros y flujo de validación
- Mejor mejora posible: reforzar la experiencia del usuario para que el formulario se sienta más completo y menos ambiguo

