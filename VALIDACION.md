# Validación de `documentos-verificables`

## Cambios aplicados

La skill se convirtió en un protocolo operativo de siete pasos: identificar el entregable, inventariar datos, asignar procedencia, resolver el estado, redactar, crear la lista de verificación y ejecutar un barrido final. Se añadieron reglas explícitas para distinguir datos aportados, derivados, conocimiento estable y datos ausentes o no resueltos.

También se reforzaron los puntos que habían mostrado ambigüedad durante la evaluación: límites de la lista de verificación para evitar ampliar el encargo sin necesidad; tratamiento de datos caducables; contradicciones; previsiones; referencias no localizadas; insuficiencia de datos esenciales; autocontrol de salida; y propagación de marcas existentes como **tokens inmutables**, copiados carácter por carácter.

## Validación estructural

La skill pasó el validador oficial `quick_validate.py` sin errores después de instalar `PyYAML`, que faltaba en el entorno.

## Pruebas funcionales

Se ejecutó `promptfoo` 0.120.19 con `gpt-5-mini` sobre 12 escenarios:

| Área | Escenario probado |
|---|---|
| Previsiones | Separar fecha prevista de fecha real |
| Ausencias | No inventar versión, fecha, identificador ni URL |
| Derivaciones | Mostrar y auditar una suma |
| Contradicciones | No elegir silenciosamente entre dos importes |
| Propagación | Conservar una marca existente literalmente |
| Referencias | No inventar una norma, cita o URL |
| Literalidad | Preservar una cifra aparentemente errónea |
| Caducidad | Señalar la vigencia de precio y versión |
| Hipótesis | Etiquetar un escenario hipotético mezclado con hechos |
| Citas | No inventar una cita textual ni un nombre |
| Insuficiencia | Marcar los datos esenciales ausentes antes de firmar |
| Entrega | Separar documento y lista de verificación |

Resultado final: **12/12 aprobados, 100 %, 0 errores de ejecución**. La evaluación consumió 51.183 tokens y registró 0,0254 USD aproximadamente en la ejecución de referencia anterior; el coste de la última ejecución depende del registro de promptfoo y no se usa como criterio de calidad.

## Interpretación

La batería confirma el comportamiento esperado en los casos diseñados. No constituye una garantía matemática: las pruebas usan un único modelo, una ejecución por caso y aserciones observables. Deben repetirse con nuevas formulaciones si la skill se va a emplear en un flujo de alto riesgo, especialmente para documentos legales, financieros, médicos o destinados a firma.
