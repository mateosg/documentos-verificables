---
name: documentos-verificables
description: "Crear o transformar documentos factuales preservando la procedencia de cada dato. Usar para informes, resúmenes, propuestas, documentación, presentaciones, hojas de cálculo, fichas, correos y README que puedan enviarse, publicarse, firmarse o alimentar otro trabajo; marcar como [VERIFICAR: ...] todo dato ausente, incierto, contradictorio o de alto riesgo que no esté respaldado."
---

# Documentos verificables

Aplicar esta skill a cualquier documento que pueda leerse como factual. La prioridad es la **trazabilidad**, no la apariencia de completitud. No rellenar huecos con valores plausibles.

## Excepciones de alcance

No aplicar el marcado de huecos a ficción, lluvia de ideas, maquetas, ejemplos, datos de prueba o borradores que el usuario haya pedido explícitamente como especulativos. Identificar dentro del resultado cualquier parte hipotética para que no se confunda con un hecho. Si la petición mezcla contenido factual e hipotético, separar ambas partes y etiquetar la segunda.

## Protocolo obligatorio

Seguir estos pasos antes de entregar:

1. **Identificar el entregable.** Determinar qué texto se presenta como documento factual y qué partes son instrucciones, hipótesis, ejemplos o comentarios.
2. **Inventariar los datos.** Revisar individualmente cada cifra, unidad, porcentaje, fecha, plazo, nombre, cargo, organización, identificador, precio, dirección, contacto, versión, enlace, cita, referencia y afirmación de hecho.
3. **Asignar procedencia.** Para cada dato, clasificarlo como una de estas categorías:
   - **Fuente aportada:** aparece explícitamente en el material recibido. Escribirlo tal cual; no redondear, corregir, normalizar ni convertir unidades en silencio.
   - **Derivado:** se obtiene mediante una operación explícita y reproducible sobre datos aportados. Mostrar la operación o explicar la relación; incluirlo en la lista de verificación.
   - **Conocimiento estable:** afirmación general, ampliamente estable y expresada en voz propia. No usar esta categoría para cifras, estadísticas, fechas, versiones, precios, nombres propios, identificadores, citas, referencias bibliográficas, normas o URLs.
   - **Ausente o no resuelto:** no aparece, aparece de forma ambigua, depende de una suposición, está en conflicto entre fuentes o solo se presenta como previsión. Marcarlo.
4. **Resolver el estado.** No convertir una previsión, objetivo, estimación, aproximación o dato mencionado indirectamente en un hecho. No escoger silenciosamente entre fuentes contradictorias. No tratar una marca `[VERIFICAR: ...]` como un dato confirmado.
5. **Redactar el documento.** Incluir solo datos confirmados o derivados justificables. Insertar las marcas en el punto exacto donde falta el dato. Mantener el texto de la marca buscable y con este formato exacto:

   ```text
   [VERIFICAR: qué dato falta o está en duda; valor candidato si existe; dónde comprobarlo]
   ```

   Hacer la marca específica: preferir `[VERIFICAR: fecha real de firma; el borrador solo contiene una fecha prevista]` a `[VERIFICAR: fecha]`.
6. **Crear la lista de verificación fuera del documento.** Incluir una entrada por cada marca del documento, ordenada por riesgo. Para cada entrada indicar: dato a comprobar, estado o valor candidato, fuente o ubicación donde comprobarlo y consecuencia si es incorrecto. Mantener el candidato fuera del documento cuando no esté confirmado.
7. **Ejecutar el barrido final.** Buscar de nuevo todas las cifras, fechas, nombres, identificadores, enlaces, citas y afirmaciones de hecho. Si alguno no tiene procedencia suficiente, convertirlo en marca antes de entregar.

## Reglas de decisión

- Escribir literalmente lo que consta en una fuente, incluso si parece una errata. Si se normaliza, declarar la normalización y conservar el valor original cuando sea relevante.
- Escribir un cálculo derivado solo si todos sus operandos están disponibles y la operación puede auditarse. No derivar un dato a partir de otro que ya está marcado.
- Usar conocimiento propio únicamente para explicaciones generales y estables. Si la afirmación requiere exactitud normativa, temporal o bibliográfica, marcarla o verificarla externamente.
- No inventar ni completar por simetría clientes, personas, organizaciones, cargos, números de expediente, modelos, precios, fechas, versiones, DOI, títulos, páginas, normas, citas o URLs.
- No transformar una dirección de búsqueda, un repositorio o una organización mantenedora en una referencia concreta. Es válido indicar en la lista dónde buscar; no es válido presentar como confirmada una referencia no localizada.
- Para una contradicción, conservar los valores relevantes, indicar qué fuentes discrepan y marcar cuál debe resolverse. Elegir una fuente solo cuando su prioridad temporal o documental esté explícitamente justificada.
- Para datos caducables —precios, cargos, direcciones, versiones, disponibilidad, normativa— indicar la fecha de la fuente y marcar la vigencia si no está confirmada.
- Si una fuente dice que algo se acordó o se trató en otra reunión, no inferir la fecha, participantes ni contenido de esa reunión.
- Reproducir una cita literalmente o parafrasearla sin comillas; no mejorarla ni atribuirla a una fuente que no la contiene.
- Tratar cada marca existente como un **token inmutable**: copiarla carácter por carácter, incluido su texto interno, al reformatear o pasar el documento a otro agente. No resumirla, corregirla, traducirla, cambiar su puntuación ni sustituirla por otra marca. No borrarla, rellenarla ni convertirla en texto definitivo sin una fuente nueva.
- Si faltan datos esenciales para que el documento se sostenga, explicarlo antes de generar un texto que parezca terminado. Se puede entregar una estructura incompleta, pero debe quedar claro qué impide validarla.

## Límites de la lista de verificación

La lista sirve para resolver huecos, no para ampliar el encargo. No añadir especificaciones, riesgos, campos o recomendaciones que el usuario no haya pedido salvo que sean necesarios para evitar que el documento resulte engañoso. Si se añaden por seguridad, distinguirlos como observaciones adicionales y no presentarlos como datos de la fuente.

Para un campo ausente sin candidato, escribir `Valor candidato: ninguno en las fuentes aportadas`. Para una previsión, conservar el valor previsto solo como candidato en la lista y describir que no es un hecho. Para una contradicción, listar todos los valores en conflicto y la fuente de cada uno.

## Formato de entrega por defecto

Entregar en este orden, salvo que el formato solicitado exija otra presentación:

### 1. Documento

El contenido solicitado, con las marcas `[VERIFICAR: ...]` insertadas y sin candidatos no confirmados presentados como hechos.

### 2. Lista de verificación

Una lista separada y ordenada por riesgo. Mantener una correspondencia uno-a-uno entre las marcas del documento y sus entradas.

### 3. Limitaciones, solo si proceden

Indicar contradicciones, datos caducables, punto débil del documento y material que lo reforzaría. No convertir esta sección en una investigación nueva ni en una lista de hechos no solicitados.

## Autocontrol de salida

Antes de entregar, comprobar:

- Cada dato de alto riesgo tiene procedencia explícita o está marcado.
- Cada previsión sigue siendo una previsión.
- Cada cálculo muestra sus operandos o relación.
- Ninguna contradicción se resolvió en silencio.
- No hay URLs, citas, autores, títulos, DOI, números de norma o identificadores inventados.
- Cada marca usa exactamente `[VERIFICAR: ...]`, es útil y aparece también en la lista.
- La lista no contiene candidatos que el documento presente como hechos.
- Las marcas sobreviven al formato o exportación solicitados.
- Las limitaciones no se ocultan para que el documento parezca más completo.

## Ejemplo mínimo

**Documento:**

> El contrato se firmó el [VERIFICAR: fecha real de firma; el borrador solo contiene una fecha prevista] por un importe de 143.652,58 EUR.

**Lista de verificación:**

> **Fecha de firma.** Valor candidato: 15/09/2023, pero la fuente lo presenta como previsto y no como hecho. Comprobar en el contrato firmado o acta de firma. Un error afecta a los vencimientos posteriores.

El importe se escribe porque consta literalmente en la fuente; la fecha permanece marcada porque solo es una previsión.
