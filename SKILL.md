---
name: documentos-verificables
description: "Crear o transformar documentos factuales preservando la procedencia de cada dato y manteniendo un alcance cerrado. Usar para informes, resúmenes, propuestas, documentación, presentaciones, hojas de cálculo, fichas, correos y README que puedan enviarse, publicarse, firmarse o alimentar otro trabajo; marcar con [VERIFICAR: ...] solo los datos necesarios para sostener afirmaciones que sí formen parte del entregable y que estén ausentes, sean candidatos no confirmados o estén en conflicto."
---

# Documentos verificables

Aplicar esta skill a documentos que puedan leerse como factuales. La prioridad es la trazabilidad **dentro del encargo**, no la apariencia de completitud ni la enumeración de todo lo que podría faltar.

## Principio de alcance cerrado

Definir primero qué afirmaciones, campos o secciones pide el entregable. No ampliar ese conjunto durante la revisión.

- Redactar únicamente datos presentes en las fuentes aportadas, datos derivados de ellas de forma explícita o contenido general estable que sea necesario para expresar el entregable.
- Mantener en el documento solo los campos y afirmaciones que la tarea solicita o que sean necesarios para que el texto solicitado sea comprensible.
- Omitir los campos no solicitados aunque sean habituales en ese tipo de documento. Su ausencia no es un problema y no debe mencionarse.
- Crear una marca `[VERIFICAR: ...]` solo cuando el documento vaya a redactar una afirmación necesaria y el dato que la sostiene sea ausente, candidato no confirmado, ambiguo o contradictorio.
- No crear campos, preguntas, recomendaciones ni verificaciones por simetría, por plantilla o porque normalmente aparezcan en documentos parecidos.
- No escribir una lista general de datos faltantes. Una carencia solo existe para esta skill cuando está representada por una marca en el documento.

## Estados de los datos

Distinguir exactamente estos estados:

1. **Dato confirmado:** consta literalmente en una fuente aportada o se deriva mediante una operación explícita y reproducible cuyos operandos constan. Puede aparecer en el documento.
2. **Dato candidato:** aparece en una fuente como previsto, estimado, aproximado, propuesto, sujeto a confirmación o en otra forma no definitiva. Puede servir para orientar la redacción, pero no debe presentarse como hecho. Si el entregable necesita ese dato, conservar el candidato solo en la lista de verificación y marcar el lugar correspondiente en el documento.
3. **Dato ausente imprescindible:** no consta en las fuentes, pero el documento sí necesita ese dato para sostener una afirmación que se ha pedido redactar. Marcarlo en el documento y crear su única entrada correspondiente en la lista.
4. **Dato en conflicto o ambiguo:** las fuentes no permiten determinar un único valor. Si el entregable necesita afirmarlo, conservar el conflicto y marcarlo; no elegir en silencio.
5. **Dato irrelevante para el entregable:** no hace falta para lo que se pidió. Omitirlo y no mencionarlo, aunque esté ausente.

El conocimiento general y estable puede usarse solo para explicar el documento cuando sea necesario. No usarlo para completar cifras, fechas, precios, versiones, nombres propios, identificadores, citas, referencias, normas o URLs.

## Protocolo obligatorio

Seguir estos pasos antes de entregar:

1. **Fijar el alcance.** Escribir mentalmente una lista breve de las afirmaciones o campos que el usuario solicita. No añadir campos implícitos por costumbre.
2. **Seleccionar las fuentes relevantes.** Usar solo el material aportado y, si el usuario lo pide, las fuentes externas que se hayan consultado. No convertir la ausencia de una fuente no solicitada en una carencia.
3. **Clasificar cada dato necesario.** Etiquetarlo como confirmado, candidato, ausente imprescindible, en conflicto/ambiguo o irrelevante.
4. **Redactar dentro del alcance.** Incluir datos confirmados y derivados justificables. Omitir campos irrelevantes. No presentar candidatos como hechos.
5. **Marcar solo lo necesario.** Insertar una marca en el punto exacto donde un dato candidato, ausente imprescindible o en conflicto impide sostener una afirmación que sí forma parte del entregable. Usar siempre este formato exacto:

   ```text
   [VERIFICAR: qué dato está pendiente; valor candidato si existe; dónde comprobarlo]
   ```

   Si no existe un valor candidato, describir la comprobación sin inventar uno; no escribir una etiqueta de “valor candidato” vacía.
6. **Construir la lista por correspondencia.** Crear exactamente una entrada por cada marca `[VERIFICAR: ...]` presente en el documento. No crear entradas adicionales. Si el documento no contiene marcas, no crear una lista de verificación vacía ni una sección de ausencias.
7. **Ejecutar el barrido de alcance.** Comprobar que no se han añadido campos, verificaciones o carencias que no sean necesarios para las afirmaciones redactadas.

## Reglas de decisión

- Escribir literalmente lo que consta en una fuente, incluso si parece una errata. Si se normaliza, declarar la normalización y conservar el original cuando sea relevante.
- Escribir un cálculo derivado solo si todos sus operandos están disponibles y la operación puede auditarse. No derivar un dato desde otro que está marcado.
- Para un candidato, conservar el valor y su estado únicamente en la lista de verificación; en el documento debe quedar claro que no es un hecho mediante la marca.
- Para un dato ausente sin candidato, describir directamente qué debe comprobarse en la marca o en su entrada; no usar “Valor candidato: ninguno” ni equivalentes.
- Para una contradicción, conservar los valores relevantes y sus fuentes solo si la afirmación forma parte del entregable. Marcar la resolución pendiente y crear una única entrada para esa marca.
- No inventar ni completar clientes, personas, organizaciones, cargos, identificadores, modelos, precios, fechas, versiones, DOI, títulos, páginas, normas, citas o URLs.
- No transformar un repositorio, registro u organización mantenedora en una referencia concreta no localizada. Es válido indicar dónde comprobar el dato pendiente, pero solo dentro de una entrada asociada a una marca necesaria.
- Para datos caducables —precios, cargos, direcciones, versiones, disponibilidad o normativa— señalar la fecha de la fuente solo si ese dato forma parte del entregable o es necesario para interpretar una afirmación redactada.
- Si una fuente menciona otra reunión o documento sin concretar, no inferir su fecha, participantes ni contenido. Marcarlo solo si el entregable necesita afirmarlo.
- Reproducir una cita literalmente o parafrasearla sin comillas; no mejorarla ni atribuirla a una fuente que no la contiene.
- Tratar cada marca existente como un **token inmutable**: copiarla carácter por carácter, incluido su texto interno, al reformatear o pasar el documento a otro agente. No resumirla, corregirla, traducirla, cambiar su puntuación ni sustituirla por otra marca.
- Si faltan tantos datos necesarios que el entregable no puede sostenerse, decirlo de forma breve y marcar solo esos datos necesarios. No construir una plantilla rellenada con campos ausentes no solicitados.

## Lista de verificación mínima

La lista no es un inventario de carencias ni una ficha técnica ampliada. Solo puede existir como reflejo de las marcas del documento.

Para cada marca, incluir:

- **Dato pendiente:** qué afirmación del documento no puede sostenerse todavía.
- **Estado:** `candidato`, `ausente imprescindible` o `en conflicto/ambiguo`.
- **Valor candidato:** incluirlo únicamente si aparece en la fuente y está sin confirmar. Si no existe, omitir esta línea por completo.
- **Dónde comprobarlo:** fuente, documento o registro concreto que debe consultarse.
- **Consecuencia:** solo si es útil para entender por qué ese dato es necesario.

No escribir frases como `Valor candidato: ninguno en las fuentes aportadas`, `no se proporcionó ningún valor candidato`, `faltan además`, ni equivalentes. Cuando no haya candidato, basta con indicar el dato pendiente y dónde comprobarlo.

## Formato de entrega

Adaptar el formato a la petición. Por defecto:

### 1. Documento

Entregar solo el contenido solicitado. Incluir las marcas necesarias dentro del texto. No añadir campos ausentes que el usuario no pidió.

### 2. Lista de verificación

Incluirla solo si el documento contiene al menos una marca. Debe haber una correspondencia uno-a-uno entre marcas y entradas. Si no hay marcas, omitir esta sección.

### 3. Limitaciones

Añadirlas solo cuando una limitación afecte a una afirmación redactada. No usar esta sección para enumerar carencias hipotéticas o campos habituales no solicitados.

## Autocontrol de salida

Antes de entregar, comprobar:

- El documento no contiene afirmaciones ni campos fuera del alcance solicitado.
- Cada dato que aparece tiene procedencia suficiente o está marcado.
- Cada candidato sigue identificado como candidato y no como hecho.
- Cada dato ausente marcado es imprescindible para una afirmación que sí aparece en el documento.
- Cada marca usa exactamente `[VERIFICAR: ...]` y conserva un texto útil.
- El número de entradas de la lista de verificación coincide exactamente con el número de marcas del documento.
- Si no hay marcas, no hay lista de verificación ni inventario de ausencias.
- No existe ninguna línea `Valor candidato` cuando no hay candidato.
- No hay verificaciones independientes sobre datos ausentes que no estén representados por una marca.
- No se han inventado cifras, fechas, nombres, identificadores, citas, referencias, normas ni URLs.
- Las marcas existentes se han copiado literalmente y sobreviven al formato solicitado.

## Ejemplos de alcance cerrado

### Fuente completa: no marcar

**Petición:** “Redacta una nota con el nombre y la fecha de lanzamiento.”

**Fuente:** “Producto: Atlas. Lanzamiento: 12/03/2026.”

**Documento:**

> El producto Atlas se lanzó el 12/03/2026.

No crear marcas ni lista de verificación. No mencionar que faltan precio, versión, fabricante o URL: esos datos no forman parte de la petición.

### Candidato explícito: marcar y conservarlo fuera del documento

**Petición:** “Redacta la fecha de entrega prevista como parte de una nota de estado.”

**Fuente:** “La entrega está propuesta para el 20/04/2026, pendiente de confirmación.”

**Documento:**

> La entrega queda prevista para [VERIFICAR: fecha definitiva de entrega; la fuente propone el 20/04/2026, pero indica que está pendiente de confirmación].

**Lista de verificación:**

> **Dato pendiente:** fecha definitiva de entrega.
> **Estado:** candidato.
> **Valor candidato:** 20/04/2026.
> **Dónde comprobarlo:** confirmación escrita del responsable de la entrega.

### Ausencia necesaria: una marca y una entrada

**Petición:** “Redacta una nota indicando el número de expediente.”

**Fuente:** “La solicitud corresponde al proyecto Atlas.”

**Documento:**

> La solicitud corresponde al proyecto Atlas y tiene el número de expediente [VERIFICAR: número de expediente necesario para identificar la solicitud; comprobar en el registro del proyecto].

**Lista de verificación:**

> **Dato pendiente:** número de expediente necesario para identificar la solicitud.
> **Estado:** ausente imprescindible.
> **Dónde comprobarlo:** registro del proyecto.

No escribir una línea de valor candidato: no existe ninguno.

### Ausencias irrelevantes: omitirlas

**Petición:** “Resume el producto y su función.”

**Fuente:** “Producto: Sensor Delta. Función: medir temperatura. No constan versión, precio, fabricante ni URL.”

**Documento:**

> El Sensor Delta sirve para medir temperatura.

No marcar ni mencionar versión, precio, fabricante o URL: no son necesarios para el resumen solicitado.

### Candidato y ausencia en un mismo documento

Si una petición necesita dos datos y la fuente aporta un candidato para uno pero ninguno para el otro, crear dos marcas —una por dato— y exactamente dos entradas. La primera puede tener `Valor candidato`; la segunda no debe tener ninguna línea equivalente si no existe candidato.
