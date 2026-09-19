# Validación de `documentos-verificables`

## Revisión de alcance cerrado

Esta revisión corrige un problema de sobreproducción: la versión anterior podía convertir campos habituales pero no solicitados en carencias y añadirlos a la lista de verificación. La regla central ahora es que el agente debe fijar primero el alcance del entregable y no ampliarlo durante la auditoría.

Los cambios principales son:

- **Alcance cerrado:** solo se consideran las afirmaciones y campos que pide el entregable.
- **Marcas condicionadas:** solo se crea `[VERIFICAR: ...]` cuando el documento necesita una afirmación y su dato es candidato, ausente imprescindible o está en conflicto.
- **Omisión de irrelevantes:** los campos no solicitados se omiten sin mencionarlos, aunque la fuente diga que no constan.
- **Correspondencia estricta:** la lista de verificación contiene exactamente una entrada por cada marca presente en el documento y ninguna entrada adicional.
- **Candidatos separados:** un candidato explícito se conserva como candidato en la lista, nunca como hecho en el documento.
- **Ausencias sin candidato:** no se escribe ninguna línea `Valor candidato` ni equivalente cuando no existe un candidato.
- **Autocontrol de alcance:** se comprueba que no haya campos, preguntas ni verificaciones introducidos por simetría o por plantilla.

## Estados diferenciados

La skill distingue entre dato confirmado, dato candidato, dato ausente imprescindible, dato en conflicto o ambiguo y dato irrelevante para el entregable. Esta clasificación evita confundir “no aparece en la fuente” con “debe verificarse”: solo el dato ausente imprescindible se marca.

## Validación estructural

La skill pasó el validador oficial `quick_validate.py` sin errores.

## Pruebas funcionales

Se ejecutó `promptfoo` con `gpt-5-mini` sobre la batería anterior y cinco pruebas nuevas de alcance cerrado. Resultado: **17/17 aprobadas, 100 %, 0 fallos y 0 errores de ejecución**.

Las cinco pruebas nuevas comprueban:

1. Una fuente con todos los datos necesarios no genera ninguna marca ni carencia hipotética.
2. Un candidato explícito se conserva fuera del documento y se representa con una única marca y una entrada.
3. Un dato ausente imprescindible produce una marca y una única entrada correspondiente.
4. Datos adicionales ausentes pero irrelevantes se omiten completamente.
5. No aparece `Valor candidato` ni una frase equivalente cuando no existe candidato.

## Interpretación

La batería confirma el comportamiento esperado en los casos diseñados, incluido el principio de alcance cerrado. No constituye una garantía matemática: las pruebas usan un único modelo y una ejecución por caso. En documentos legales, financieros, médicos o destinados a firma, se recomienda mantener revisión humana y, cuando sea posible, validaciones deterministas adicionales.
