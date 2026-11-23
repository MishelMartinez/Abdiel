# Biblioteca de Catecismos — versión 6

Sitio web responsive sin dependencias externas. Incluye las 33 preguntas (1–33) del JSON proporcionado. **Las respuestas son visibles; cada sección de referencias bíblicas tiene su propio acordeón.**

## Cómo abrirlo

Abre `index.html` con doble clic: las 33 preguntas se ven incluso sin servidor ni conexión. También se puede publicar el contenido de esta carpeta en GitHub Pages (Settings > Pages > Deploy from branch > main > root).

## Cómo agregar nuevos catecismos

1. Coloca el nuevo JSON en `data/`. Su formato puede ser un arreglo de preguntas o `{ "preguntas": [...] }`.
2. Agrega al arreglo `catecismos` de `data/catalogo.json` un registro con `id`, `titulo`, `subtitulo`, `archivo` (por ejemplo `data/otro-catecismo.json`) y `activo: true`.
3. Publica los archivos actualizados en GitHub Pages. **Los catecismos adicionales requieren un servidor web o GitHub Pages**; el primer catecismo permanece incrustado como respaldo para que abra por doble clic. Si actualizas las preguntas del Catecismo Menor en JSON, publícalas en GitHub Pages; para actualizar también la copia sin conexión incluida en HTML se debe regenerar el HTML.

Las referencias se muestran por inciso, sin alterar ni completar citas. La pregunta 33 es incompleta en el original.

## Visor de pasajes (versión 3)

Cada cita dentro del acordeón muestra un botón con icono de ojo cuando el JSON contiene `Pasaje`. Al pulsarlo se abre una ventana accesible con la referencia y el texto, sin navegación externa. Se cierra con la X, clic fuera o tecla Escape. Se admite la estructura anterior de citas en texto, pero sin botón de ojo si no hay pasaje. La página incluye los pasajes iniciales incrustados para funcionar al abrir el HTML localmente.

## Navegación (versión 6)

Las preguntas se ordenan numéricamente de menor a mayor (independientemente del orden del JSON). Se muestran 6 preguntas por página (33 preguntas = 6 páginas) y solo aparece paginación cuando hay más de 6 preguntas. Al introducir solo dígitos (por ejemplo, 25), la búsqueda devuelve únicamente la pregunta con ese número exacto. Al introducir palabras, busca en preguntas, respuestas y referencias bíblicas. La búsqueda reinicia la página a la primera; cambiar de catecismo también reinicia la paginación. No se crean preguntas faltantes. Se conserva el visor de versículos con el icono de ojo.

## Datos integrados (noviembre de 2026)

Se integró el archivo `catecismo-menor.json` recibido, con las preguntas 1–33, sin modificar sus respuestas ni textos de pasajes. La pregunta 33 figura incompleta en el origen. Las citas se leen de `referenciasBiblicas[].citas[].Pasaje` y las referencias comparativas opcionales se preservan en el JSON. La página incluye copia embebida para abrir `index.html` sin servidor y un JSON externo para GitHub Pages.
