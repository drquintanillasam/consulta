---
name: radioskillmd
description: Interpretación de radiografías digitales en primer nivel de atención. Genera reportes radiológicos ultrabreves (máximo 40 palabras) listos para integrar en nota clínica electrónica. Usar esta skill siempre que el usuario suba una imagen radiográfica (Rx), solicite lectura o interpretación de placa, pida reporte radiológico, mencione hallazgos en radiografía, o requiera impresión diagnóstica basada en imagen. También activar si el usuario menciona "Rx", "placa", "radiografía", "rayos X", "X-ray" o "reporte radiológico", incluso si no adjunta imagen en el primer mensaje.
---

## Propósito

Generar un reporte radiológico ultrabreve, preciso y clínicamente útil a partir de una radiografía digital, listo para copiar e integrar directamente en una nota clínica electrónica de primer nivel de atención.

## Reglas absolutas del reporte

| Regla | Especificación |
|-------|----------------|
| Extensión máxima | 40 palabras |
| Formato | Un solo párrafo continuo, redacción corrida |
| Idioma | Español médico, terminología ACR |
| Contenido permitido | Hallazgos radiográficos relevantes + impresión diagnóstica |
| Estructuras normales | Mencionar brevemente solo las principales cuando sea pertinente |
| Técnica y proyección | Omitir, salvo que la calidad limite la interpretación |
| Datos administrativos | Omitir siempre (fecha, nombre, ID, proyección, equipo) |
| Estudio sin hallazgos | Indicar claramente en forma breve |
| Formato de entrega | Texto plano, sin bloque de código, sin etiquetas de lenguaje, sin encabezados, sin listas, sin saltos de línea |
| Lenguaje especulativo | Prohibido; solo describir lo observable |

## Referencia terminológica

Utilizar como referencia los criterios y estándares del American College of Radiology (ACR) para nomenclatura y descriptores radiológicos. No citar la fuente en el reporte. Mantener concordancia terminológica ACR en todos los hallazgos descritos.

## Flujo de trabajo

### 1. Recepción de imagen

Verificar que la imagen proporcionada corresponda a una radiografía digital. Si la imagen no es una radiografía o no es interpretable, responder indicando la limitación en una oración breve y no generar reporte.

### 2. Evaluación de calidad técnica

Evaluar si la calidad de la imagen permite interpretación adecuada. Si existen limitaciones técnicas significativas (rotación excesiva, subexposición, sobreexposición, artefactos, corte anatómico), incluir una mención breve dentro del reporte sin consumir más de 8 palabras del límite total.

### 3. Análisis sistemático silencioso

Realizar internamente una revisión sistemática según la región anatómica antes de redactar el reporte. Este análisis no se incluye en la salida; solo informa la redacción final.

| Región | Revisión sistemática interna |
|--------|------------------------------|
| Tórax PA/AP | Silueta cardíaca, mediastino, hilios, campos pulmonares, ángulos costofrénicos, estructuras óseas, tejidos blandos |
| Abdomen | Distribución de gas intestinal, niveles hidroaéreos, siluetas de órganos sólidos, calcificaciones, estructuras óseas |
| Extremidades | Alineación, cortical, trabécula, espacios articulares, tejidos blandos |
| Columna | Alineación, cuerpos vertebrales, espacios discales, pedículos, tejidos paravertebrales |
| Cráneo | Calota, suturas, silla turca, senos paranasales, estructuras de la base |
| Senos paranasales | Neumatización, niveles hidroaéreos, integridad ósea, septum |
| Mano/muñeca (edad ósea) | Núcleos de osificación según Greulich-Pyle |

### 4. Generación del reporte

Redactar el reporte siguiendo estrictamente todas las reglas de la tabla de reglas absolutas. El texto debe ser autocontenido, sin depender de contexto externo para su comprensión.

## Ejemplos de reportes correctos

**Rx tórax sin hallazgos:**
Silueta cardíaca de tamaño normal, campos pulmonares sin opacidades ni consolidaciones, senos costofrénicos libres, mediastino sin ensanchamiento, estructuras óseas sin lesiones. Sin hallazgos patológicos.

**Rx tórax con neumonía:**
Opacidad alveolar en lóbulo inferior derecho con broncograma aéreo. Silueta cardíaca normal, seno costofrénico izquierdo libre. Impresión: consolidación lobar inferior derecha compatible con proceso neumónico.

**Rx rodilla con fractura:**
Trazo de fractura transverso en meseta tibial lateral con depresión articular de aproximadamente 5 mm. Sin derrame articular significativo. Impresión: fractura de meseta tibial lateral con depresión.

**Rx abdomen con obstrucción:**
Asas de intestino delgado dilatadas con niveles hidroaéreos escalonados. Ausencia de gas en marco cólico distal. Impresión: patrón radiológico compatible con obstrucción intestinal mecánica.

**Imagen de calidad limitada:**
Calidad técnica limitada por rotación significativa. Campos pulmonares sin opacidades evidentes, silueta cardíaca aparentemente normal. Se sugiere repetir estudio con técnica adecuada para valoración confiable.

## Reglas de operación

1. Nunca exceder 40 palabras en el reporte final
2. Nunca incluir encabezados, listas, viñetas ni saltos de línea en el reporte
3. Nunca usar bloques de código ni etiquetas de formato
4. Nunca especular más allá de lo visible en la imagen
5. Nunca incluir recomendaciones clínicas, tratamiento ni seguimiento dentro del reporte
6. Nunca omitir hallazgos patológicos visibles por mantener brevedad; si es necesario, priorizar hallazgos por relevancia clínica
7. Si el usuario proporciona contexto clínico, utilizarlo para orientar la búsqueda de hallazgos pero no incluir datos clínicos en el reporte
8. Si el usuario solicita información adicional fuera del reporte (diagnósticos diferenciales, plan de estudio), proporcionarla por separado, nunca dentro del párrafo del reporte
9. Entregar el reporte directamente como texto plano sin preámbulo explicativo
