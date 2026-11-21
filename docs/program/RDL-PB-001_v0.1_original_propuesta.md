# PLAYBOOK OPERACIONAL DE INVESTIGACIÓN Y DESARROLLO TECNOLÓGICO

## Propuesta de marco operativo para la investigación, evaluación, validación y transferencia de tecnología

**Identificador:** RDL-PB-001\
**Versión propuesta:** 0.1\
**Estado:** Propuesta para revisión técnica\
**Nivel documental:** Operacional\
**Ámbito:** Investigación computacional, caracterización algorítmica, experimentación controlada, validación tecnológica y acumulación de conocimiento de ingeniería.



---



# 1. Propósito y mandato operativo

## 1.1. Propósito

Establecer un sistema operativo reproducible, trazable y progresivamente automatizable para transformar candidatos tecnológicos en resultados de investigación, decisiones de ingeniería y activos reutilizables.

El Playbook define los procedimientos, criterios, contratos de información, mecanismos de control y condiciones de decisión que regulan el ciclo de investigación y desarrollo tecnológico.

Su propósito no es maximizar la cantidad de ejecuciones, experimentos o documentos producidos. Es maximizar la capacidad del laboratorio para obtener conocimiento técnicamente válido y convertirlo en tecnología útil, reduciendo el coste marginal de investigar candidatos sucesivos.

## 1.2. Objetivos operativos

El sistema deberá:

1. Estandarizar la admisión y caracterización inicial de candidatos.
2. Convertir objetivos generales en preguntas de investigación verificables.
3. Seleccionar métodos experimentales compatibles con cada pregunta.
4. Reutilizar protocolos, herramientas e infraestructura cuando exista compatibilidad demostrable.
5. Detectar defectos, limitaciones y resultados negativos con un coste proporcional a su importancia.
6. Producir evidencia reproducible y suficiente para fundamentar decisiones.
7. Distinguir entre ausencia de evidencia, evidencia insuficiente y evidencia contraria a una hipótesis.
8. Identificar qué conclusiones son válidas para el candidato evaluado y cuáles pueden transferirse a otros contextos.
9. Conservar el conocimiento generado de forma recuperable y vinculado a su procedencia.
10. Mejorar los procedimientos del laboratorio mediante resultados observados, no mediante supuestos de eficiencia.

## 1.3. Principio de productividad tecnológica

La productividad del laboratorio se evaluará por su capacidad de resolver incertidumbres relevantes y tomar mejores decisiones por unidad de recursos invertidos.

La cantidad de algoritmos implementados, pruebas ejecutadas o candidatos descartados no constituye, por sí sola, una medida de productividad tecnológica.

Un candidato descartado puede generar conocimiento valioso. Un candidato aprobado puede no aportar ninguna ventaja competitiva. Una infraestructura compleja puede ser improductiva si no mejora las decisiones, la calidad de la evidencia o el coste de los ciclos posteriores.

La evaluación económica del laboratorio deberá considerar tanto el resultado inmediato de una investigación como su contribución verificable a la capacidad futura de desarrollo.



---



# 2. Autoridad documental y alcance

## 2.1. Relación con la especificación estratégica

La especificación estratégica establece la misión, las prioridades de inversión, los programas y los criterios de dirección del laboratorio.

El presente Playbook establece cómo ejecutar operacionalmente esas prioridades.

No está autorizado a modificar por interpretación propia:

- los objetivos estratégicos aprobados;
- los límites de los programas de investigación;
- las restricciones normativas de un entorno experimental;
- los contratos técnicos vigentes;
- las definiciones canónicas de un algoritmo;
- los criterios de aceptación formalmente establecidos.

Cuando una investigación encuentre una contradicción entre documentos, deberá registrar el conflicto, identificar las fuentes afectadas y solicitar su resolución por el mecanismo de gobierno documental correspondiente.

No se permite corregir silenciosamente una especificación durante la implementación o la ejecución de un experimento.

## 2.2. Ámbito de aplicación

El Playbook se aplica a:

- algoritmos nuevos y variantes de algoritmos existentes;
- implementaciones computacionales;
- mecanismos de decisión y transformación de información;
- modelos y sistemas de software;
- protocolos experimentales;
- entornos de prueba;
- herramientas de análisis;
- métodos de validación;
- hipótesis de ingeniería;
- mejoras de la propia infraestructura de investigación.

La intensidad del procedimiento deberá ser proporcional al riesgo, al coste de equivocarse, a la incertidumbre relevante y a la importancia de la decisión que se pretende adoptar.

## 2.3. Fuera de alcance

Este documento no sustituye:

- la especificación estratégica;
- las especificaciones normativas particulares de cada laboratorio;
- los contratos de interfaz entre sistemas;
- la documentación matemática canónica de un algoritmo;
- los procedimientos especializados que requiera un dominio concreto;
- los documentos de organización, incorporación de personal o distribución de responsabilidades.

El Playbook establece el marco común y remite a esos documentos cuando corresponde.

## 2.4. Lenguaje normativo

Los términos se utilizarán con el siguiente significado:

- **DEBE:** requisito obligatorio para declarar conformidad con el procedimiento.
- **NO DEBE:** prohibición normativa.
- **DEBERÍA:** práctica recomendada que admite excepción justificada.
- **PUEDE:** posibilidad permitida, sujeta a las restricciones aplicables.

Las recomendaciones no se convertirán automáticamente en requisitos universales. Las excepciones a requisitos obligatorios solo podrán aprobarse mediante un procedimiento formal de modificación o desviación autorizada.



---



# 3. Taxonomía y vocabulario canónico

La taxonomía constituye un contrato semántico del laboratorio. Su finalidad es evitar que dos investigaciones utilicen una misma palabra para representar objetos diferentes o que un resultado se trate como una conclusión que no justifica.

## 3.1. Objetos de investigación

| **Término**                    | **Definición operativa**                                                                                                                                       |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Candidato tecnológico**      | Algoritmo, implementación, mecanismo, sistema o método propuesto para evaluación.                                                                              |
| **Objeto de investigación**    | Entidad concreta sobre la que se formulan preguntas y se obtiene evidencia. Puede ser un candidato, una familia de candidatos o un componente del laboratorio. |
| **Pregunta de investigación**  | Interrogante delimitado cuya respuesta puede cambiar una conclusión, decisión o acción técnica.                                                                |
| **Hipótesis**                  | Proposición contrastable que afirma una propiedad, comportamiento, relación causal o explicación.                                                              |
| **Afirmación de conocimiento** | Enunciado respaldado por evidencia, con alcance, condiciones de validez y limitaciones explícitas.                                                             |
| **Decisión de ingeniería**     | Determinación documentada de continuar, modificar, validar, transferir, archivar o detener un trabajo.                                                         |

## 3.2. Objetos del diseño experimental

| **Término**              | **Definición operativa**                                                                                          |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **Protocolo**            | Procedimiento definido para producir observaciones o resultados bajo condiciones especificadas.                   |
| **Diseño experimental**  | Combinación concreta de protocolo, objeto, configuración, condiciones y plan de medición.                         |
| **Instrumento**          | Método, prueba, herramienta o entorno utilizado para producir o examinar resultados.                              |
| **Configuración**        | Conjunto versionado de parámetros y condiciones que determina una ejecución.                                      |
| **Ejecución (*run*)**    | Instancia concreta de ejecución de un diseño experimental bajo una configuración determinada.                     |
| **Réplica**              | Ejecución adicional destinada a evaluar variabilidad, estabilidad o reproducibilidad bajo condiciones definidas.  |
| **Campaña experimental** | Conjunto coordinado de diseños y ejecuciones orientados a una misma pregunta o conjunto relacionado de preguntas. |

Una ejecución con una semilla distinta no constituye automáticamente una nueva investigación. Es una nueva ejecución dentro de un diseño, salvo que cambie el objeto de la pregunta o el propósito experimental.

Una modificación del protocolo debe registrarse como una nueva versión. No se deben combinar silenciosamente resultados de versiones distintas como si procedieran del mismo procedimiento.

## 3.3. Objetos de información y evidencia

| **Término**            | **Definición operativa**                                                                                             |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Observación**        | Dato registrado directamente durante una ejecución o inspección.                                                     |
| **Resultado derivado** | Valor obtenido mediante una transformación, cálculo o análisis de observaciones.                                     |
| **Hallazgo**           | Patrón, anomalía, relación o comportamiento identificado mediante el examen de resultados.                           |
| **Evidencia**          | Observación, resultado o conjunto de resultados pertinente para evaluar una afirmación o decisión.                   |
| **Interpretación**     | Explicación propuesta sobre el significado de una observación o resultado.                                           |
| **Conclusión**         | Síntesis de lo que la evidencia permite sostener respecto de una pregunta.                                           |
| **Limitación**         | Condición que restringe la validez, interpretación, precisión o generalización de un resultado.                      |
| **Anomalía**           | Comportamiento inesperado, inconsistente o no explicado respecto de un contrato, referencia o expectativa explícita. |

Un hallazgo no es automáticamente una explicación causal. Una correlación observada no demuestra por sí misma un mecanismo causal. Una observación reproducible tampoco garantiza que su interpretación sea correcta.

## 3.4. Objetos de conocimiento y reutilización

| **Término**                  | **Definición operativa**                                                                                    |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Activo metodológico**      | Protocolo, instrumento, herramienta, procedimiento o técnica susceptible de reutilización.                  |
| **Activo de ingeniería**     | Implementación, componente, adaptador, biblioteca, prueba o infraestructura reutilizable.                   |
| **Registro de conocimiento** | Unidad documental que conserva una afirmación, resultado, decisión, limitación o método con su procedencia. |
| **Transferencia**            | Aplicación de un resultado o activo a un contexto distinto del contexto en el que se obtuvo.                |
| **Revalidación**             | Evaluación de si un activo o una afirmación conserva su validez bajo nuevas condiciones.                    |
| **Línea base**               | Referencia explícita contra la que se comparan resultados, costes o comportamientos.                        |

La existencia de un documento no demuestra que exista conocimiento válido. La existencia de una herramienta tampoco demuestra que sea reutilizable: su utilidad debe comprobarse en un contexto de aplicación definido.



---



# 4. Modelo operativo del laboratorio

## 4.1. Flujo principal

El ciclo de investigación se organizará en las siguientes fases:

1. **Admisión:** identificar el candidato, su origen y el motivo de investigación.
2. **Caracterización:** determinar qué es el candidato, qué promete y qué se necesita conocer.
3. **Formulación:** convertir las necesidades de conocimiento en preguntas y criterios de decisión.
4. **Planificación:** seleccionar instrumentos, protocolos, condiciones y presupuesto.
5. **Ejecución:** realizar las pruebas y conservar los registros requeridos.
6. **Análisis:** transformar observaciones en resultados interpretables.
7. **Evaluación de evidencia:** contrastar hipótesis y determinar qué puede sostenerse.
8. **Decisión:** continuar, corregir, ampliar, transferir, archivar o detener.
9. **Integración:** incorporar el conocimiento y los activos reutilizables al sistema institucional.
10. **Mejora operacional:** evaluar si los resultados justifican cambios en los procedimientos o instrumentos del laboratorio.

Estas fases constituyen una estructura de control, no una secuencia rígida que obligue a ejecutar todas las actividades en todos los casos. Una prueba inicial puede justificar el descarte temprano de un candidato; un defecto de especificación puede requerir regresar a la caracterización; un resultado ambiguo puede exigir un nuevo diseño experimental.

## 4.2. Separación de responsabilidades funcionales

El sistema DEBE distinguir las siguientes responsabilidades:

- **Orquestación experimental:** administra diseños, configuraciones, ejecuciones, recursos y condiciones de terminación.
- **Objeto bajo estudio:** implementa el comportamiento del candidato evaluado.
- **Entorno experimental:** define las condiciones externas y las reglas del sistema de prueba.
- **Registro:** conserva observaciones, eventos, estados relevantes y resultados de ejecución.
- **Medición:** calcula métricas a partir de datos definidos.
- **Análisis:** compara resultados, evalúa hipótesis y produce interpretaciones.
- **Visualización:** presenta información para inspección humana sin alterar los datos experimentales.
- **Gestión del conocimiento:** conserva afirmaciones, decisiones, procedencia, activos y relaciones entre investigaciones.

Estas responsabilidades pueden implementarse en un mismo programa durante las primeras etapas. La separación semántica y contractual es obligatoria; la separación física en servicios o repositorios distintos no lo es.

## 4.3. Aislamiento experimental

Los instrumentos deberán acceder únicamente a las capacidades necesarias para cumplir su función.

Un registrador no debe alterar el objeto que observa. Una métrica no debe modificar los datos de origen. Una visualización no debe convertirse en la autoridad sobre el estado experimental. Un entorno no debe adaptar sus reglas silenciosamente en respuesta al comportamiento del candidato.

Cuando una investigación requiera una excepción —por ejemplo, instrumentación invasiva o un entorno adaptativo—, esta deberá declararse como parte del diseño experimental y evaluarse su posible efecto sobre los resultados.



---



# 5. Admisión y caracterización de candidatos

## 5.1. Registro de admisión

Todo candidato que ingrese al proceso formal DEBE disponer de un registro de admisión.

El registro incluirá, como mínimo:

- identificador único;
- denominación y versión;
- descripción funcional;
- documentación de origen;
- especificación disponible;
- estado de implementación;
- dependencias conocidas;
- capacidades declaradas;
- restricciones conocidas;
- preguntas iniciales;
- motivo de evaluación;
- recursos y limitaciones relevantes;
- estado de la información: confirmado, declarado, inferido o desconocido.

La ausencia de información no se suplirá mediante supuestos silenciosos. Se registrará como desconocida, pendiente de caracterización o no aplicable, según corresponda.

## 5.2. Declaración de capacidades

Antes de seleccionar protocolos, el laboratorio DEBERÍA disponer de una declaración estructurada de capacidades.

Esta declaración no es una descripción comercial del candidato ni una afirmación de que sus propiedades hayan sido demostradas. Es una hipótesis operacional sobre qué comportamientos puede producir y qué condiciones necesita para hacerlo.

Debe especificar:

1. **Entradas:** tipos, dimensiones, rangos, restricciones y condiciones de validez.
2. **Salidas:** tipos, estructura, significado y garantías.
3. **Estado interno:** si existe, cómo evoluciona y si puede observarse o serializarse.
4. **Transiciones:** cómo cambia el estado ante entradas y acciones.
5. **Adaptación:** si el sistema modifica su comportamiento, sus parámetros o su estado a partir de la experiencia.
6. **Dependencias:** bibliotecas, datos, servicios, recursos y condiciones de ejecución.
7. **Determinismo:** condiciones bajo las que entradas equivalentes producen resultados equivalentes.
8. **Costes:** tiempo, memoria, cómputo y otros recursos relevantes.
9. **Restricciones:** límites matemáticos, computacionales, operacionales o de dominio.
10. **Propiedades reclamadas:** afirmaciones que necesitan verificación.
11. **Propiedades desconocidas:** cuestiones que todavía no pueden determinarse.

Cada propiedad declarada debe identificarse como especificada, observada, verificada o pendiente. Estos estados no son intercambiables.

## 5.3. Caracterización inicial

La caracterización inicial tiene como finalidad reducir la incertidumbre suficiente para elegir la siguiente acción de investigación.

No pretende comprender exhaustivamente el candidato.

Debe determinar, cuando resulte aplicable:

- si la implementación corresponde a la especificación;
- si existen fallos de ejecución evidentes;
- si se cumplen los contratos básicos;
- qué entradas y estados acepta;
- qué propiedades son comprobables mediante pruebas baratas;
- qué incertidumbres impiden tomar una decisión;
- qué riesgos justifican pruebas adicionales.

La caracterización puede terminar con una decisión de descarte, corrección, investigación adicional o aceptación para una evaluación más profunda.

## 5.4. Distinción entre diseño, implementación y comportamiento observado

El laboratorio DEBE distinguir entre:

- lo que el diseño matemático afirma;
- lo que la especificación computacional prescribe;
- lo que la implementación ejecuta;
- lo que la instrumentación registra;
- lo que el análisis permite concluir.

Una propiedad demostrada matemáticamente no prueba que una implementación concreta la preserve. Una implementación que supera pruebas finitas tampoco demuestra todas las propiedades de la teoría subyacente.

Las discrepancias entre estos niveles deberán registrarse como objetos de investigación, no resolverse mediante reinterpretaciones informales.



---



# 6. Formulación de preguntas y planificación

## 6.1. Contrato de pregunta de investigación

Toda investigación formal DEBE declarar qué incertidumbre pretende resolver y qué decisión podría cambiar su respuesta.

El contrato incluirá:

- identificador de la pregunta;
- objeto o candidatos afectados;
- afirmación o hipótesis examinada;
- estado de conocimiento inicial;
- relevancia técnica o económica;
- decisión que depende de la respuesta;
- condiciones de éxito o refutación;
- incertidumbres que quedan fuera del alcance;
- presupuesto inicial;
- criterio de cierre.

Una pregunta que no pueda vincularse con una decisión, una propiedad de interés o una necesidad de conocimiento deberá reformularse antes de asignarle recursos significativos.

No se exige que toda investigación produzca una decisión inmediata de implementación. También puede ser pertinente resolver una cuestión fundacional si su respuesta reduce incertidumbre relevante para varias líneas futuras de desarrollo.

## 6.2. Descomposición de incertidumbres

Las preguntas complejas DEBERÍAN descomponerse en dimensiones evaluables cuando sus respuestas requieran métodos o evidencias diferentes.

Entre las dimensiones posibles se encuentran:

- corrección;
- cumplimiento de especificación;
- mecanismo de funcionamiento;
- estabilidad;
- sensibilidad;
- rendimiento;
- consumo de recursos;
- robustez;
- reproducibilidad;
- límites de operación;
- generalización;
- utilidad frente a alternativas;
- coste de implementación y mantenimiento.

No se impondrá una puntuación universal de incertidumbre. Cuando sea útil cuantificarla, deberá declararse el método de estimación, los supuestos y el significado de la escala utilizada.

## 6.3. Criterios de decisión anticipados

Antes de ejecutar una prueba decisiva, el diseño DEBERÍA establecer qué resultados favorecerían cada decisión plausible.

Los criterios deberán distinguir:

- condiciones necesarias;
- condiciones suficientes, cuando puedan definirse;
- umbrales operacionales;
- criterios de comparación;
- resultados inconclusos;
- condiciones de interrupción;
- evidencia adicional requerida.

Los umbrales numéricos solo serán obligatorios cuando se deriven de requisitos, restricciones, referencias o decisiones explícitas. No se introducirán cifras universales sin justificación.

La definición anticipada de criterios reduce la reinterpretación oportunista de resultados y facilita detectar cuándo un experimento no respondió a la pregunta original.



---



# 7. Selección de instrumentos y protocolos

## 7.1. Principio de selección

El laboratorio DEBE seleccionar el instrumento de menor coste que pueda resolver adecuadamente la pregunta planteada, considerando su capacidad discriminativa, validez, sensibilidad y limitaciones.

La prueba más barata no es necesariamente la mejor primera prueba. Si no puede distinguir entre las hipótesis relevantes, su bajo coste no justifica su ejecución.

La selección deberá equilibrar:

- coste de preparación;
- coste de ejecución;
- coste de análisis;
- tiempo hasta una decisión;
- capacidad para detectar el fallo buscado;
- probabilidad de resultados ambiguos;
- alcance de la conclusión;
- riesgo de falsos positivos y falsos negativos;
- reutilización potencial del protocolo.

## 7.2. Escalera de investigación

El orden inicial recomendado es:

### Nivel A. Verificación estática y contractual

Ejemplos:

- inspección de tipos e interfaces;
- comprobación de precondiciones y postcondiciones;
- análisis de invariantes;
- verificación de dimensiones y dominios;
- revisión de dependencias;
- inspección de complejidad teórica;
- validación de configuración y serialización.

### Nivel B. Pruebas computacionales controladas

Ejemplos:

- casos límite;
- pruebas unitarias;
- pruebas basadas en propiedades;
- pruebas diferenciales frente a una referencia;
- fuzzing;
- pruebas de regresión;
- análisis de errores numéricos;
- perfiles de tiempo y memoria.

### Nivel C. Análisis de estado e información

Ejemplos:

- trazado de transiciones;
- comparación de estados;
- análisis de cambios en variables internas;
- localización de la primera divergencia;
- comparación de entradas, decisiones y actualizaciones;
- intervenciones controladas para investigar mecanismos causales.

### Nivel D. Entornos dinámicos o mundos experimentales

Ejemplos:

- interacción secuencial;
- observación parcial;
- consecuencias acumulativas;
- dependencia temporal;
- adaptación del candidato;
- evaluación bajo perturbaciones;
- análisis de trayectorias.

### Nivel E. Validación externa y transferencia

Ejemplos:

- datos independientes;
- implementaciones alternativas;
- condiciones fuera del entorno original;
- comparación con métodos de referencia;
- réplica independiente;
- validación en un dominio diferente, cuando esté justificada.

Esta escalera es una política por defecto, no una secuencia universal. Una pregunta puede requerir un entorno dinámico desde el inicio, mientras que otra puede resolverse de forma concluyente con una prueba formal o computacional sencilla.

## 7.3. Compatibilidad de protocolos

Cada protocolo DEBERÍA disponer de una ficha que describa:

- preguntas que puede resolver;
- tipos de candidatos compatibles;
- entradas y precondiciones;
- variables controladas;
- variables observadas;
- métricas disponibles;
- mecanismos de registro;
- supuestos;
- limitaciones;
- costes conocidos;
- evidencia que puede producir;
- evidencia que no puede producir;
- criterios de terminación;
- versión y estado de validación.

La selección automatizada de protocolos solo será válida dentro de límites de compatibilidad explícitos. Una coincidencia de tipos de entrada no demuestra que el protocolo sea metodológicamente adecuado.

## 7.4. Adaptación y reutilización

Cuando exista un protocolo compatible, deberá reutilizarse en lugar de recrearse sin necesidad.

Toda adaptación deberá identificar:

1. qué elementos se conservan;
2. qué elementos cambian;
3. por qué el cambio es necesario;
4. qué garantías del protocolo original permanecen válidas;
5. qué garantías deben revalidarse.

Las adaptaciones sustantivas deberán generar una nueva versión identificable. La reutilización no autoriza a heredar automáticamente la validez de las conclusiones anteriores.



---



# 8. Diseño experimental y control de variables

## 8.1. Especificación del diseño

Antes de la ejecución, el diseño experimental deberá establecer:

- pregunta y objetivo;
- candidato y versión;
- protocolo y versión;
- configuración;
- condiciones iniciales;
- variables independientes;
- variables dependientes;
- variables controladas;
- factores de confusión conocidos;
- plan de muestreo o selección de casos;
- número y propósito de las réplicas;
- métricas;
- presupuesto;
- criterios de terminación;
- criterios de decisión;
- datos que deben conservarse;
- limitaciones previsibles.

No todas las investigaciones requieren un diseño estadístico complejo. El nivel de formalización deberá corresponder a la naturaleza de la pregunta y al riesgo de error.

## 8.2. Controles y referencias

Cuando sea pertinente, el diseño DEBERÍA incluir:

- una línea base;
- un método de referencia;
- una implementación de control;
- un caso negativo;
- un caso límite;
- una condición de perturbación;
- una comparación con una versión anterior.

El control elegido debe tener una función explícita. No se incluirán comparadores solo para aumentar la apariencia de rigor.

## 8.3. Semillas, aleatoriedad y replicación

Cuando intervenga aleatoriedad, el diseño deberá especificar:

- fuentes de aleatoriedad;
- semillas utilizadas;
- mecanismos de derivación de semillas;
- separación entre flujos aleatorios cuando corresponda;
- condiciones para repetir una ejecución;
- estrategia de replicación;
- criterio para resumir variabilidad.

Una semilla fija facilita reproducir una trayectoria concreta, pero no demuestra robustez estadística ni generalización. La evaluación de variabilidad requiere un diseño de muestreo adecuado a la pregunta.

## 8.4. Presupuesto experimental

Toda investigación deberá disponer de límites explícitos o criterios operacionales para el consumo de recursos cuando el coste sea material.

El presupuesto puede incluir tiempo de cómputo, memoria, número de ejecuciones, esfuerzo de análisis o coste de instrumentación.

La ampliación del presupuesto deberá justificarse por la información que se espera obtener y por la relevancia de la decisión pendiente. El coste ya invertido no constituye, por sí mismo, una razón para continuar.



---



# 9. Ejecución, registro y reproducibilidad

## 9.1. Contrato de ejecución

La ejecución deberá estar vinculada de forma inequívoca a:

- objeto de investigación;
- versión del candidato;
- versión del protocolo;
- identificador del diseño;
- configuración;
- condiciones iniciales;
- entorno y dependencias;
- semilla o estado aleatorio pertinente;
- fecha y versión del instrumental;
- estado final;
- resultados y errores;
- registros requeridos por el protocolo.

La ejecución no deberá depender de configuraciones implícitas que no puedan recuperarse posteriormente.

## 9.2. Registro de datos

El sistema de registro deberá conservar los datos necesarios para:

- verificar la ejecución;
- analizar sus resultados;
- localizar fallos;
- reproducir la trayectoria cuando sea posible;
- identificar divergencias;
- comparar ejecuciones;
- reconstruir la procedencia de las conclusiones.

La resolución del registro dependerá del experimento. Un resumen estadístico puede ser suficiente para determinadas campañas; un análisis de transiciones puede requerir trazas completas.

La decisión de no conservar un dato relevante para auditoría deberá estar justificada y documentada.

## 9.3. Identidad e integridad

Los artefactos experimentales deberán contar con identificadores estables y referencias a sus versiones.

Cuando se utilicen hashes, estos servirán para comprobar la identidad o integridad de los datos especificados. Un hash no demuestra que el contenido sea correcto, que el protocolo sea válido ni que una conclusión esté justificada.

La serialización, los formatos canónicos y los mecanismos de reproducción deberán definirse en la especificación técnica del instrumento correspondiente.

## 9.4. Niveles de reproducibilidad

El laboratorio distinguirá entre:

- **Repetibilidad de ejecución:** posibilidad de repetir una ejecución bajo las mismas condiciones controladas.
- **Reproducción de trayectoria:** posibilidad de verificar una secuencia registrada de estados y transiciones.
- **Reproducción analítica:** posibilidad de recalcular los resultados a partir de los datos conservados.
- **Reproducción experimental:** posibilidad de repetir el diseño y obtener resultados compatibles dentro de la variabilidad esperada.
- **Reproducción independiente:** obtención de resultados compatibles mediante una implementación, equipo o procedimiento independiente, según se defina en el diseño.

La etiqueta «reproducible» deberá especificar cuál de estos sentidos se ha comprobado.



---



# 10. Análisis de resultados

## 10.1. Separación entre datos e interpretación

El análisis deberá preservar una separación explícita entre:

1. datos observados;
2. resultados derivados;
3. anomalías identificadas;
4. interpretaciones propuestas;
5. hipótesis evaluadas;
6. conclusiones justificadas;
7. decisiones adoptadas.

Los cálculos deberán poder rastrearse hasta sus datos de origen y su método de transformación.

Cuando un resultado dependa de supuestos, filtros, exclusiones, normalizaciones o decisiones analíticas, estos deberán registrarse.

## 10.2. Análisis de discrepancias

Ante una discrepancia, el procedimiento recomendado es:

1. verificar la integridad de los datos;
2. comprobar la configuración y las versiones;
3. reproducir la anomalía si es posible;
4. localizar el primer punto observable de divergencia;
5. formular explicaciones alternativas;
6. diseñar una prueba discriminativa;
7. evaluar si la intervención confirma o debilita las explicaciones;
8. registrar el resultado y sus límites.

La primera divergencia observada es un punto de localización, no necesariamente la causa del fallo. Puede ser consecuencia de una divergencia anterior que no fue instrumentada o de un factor externo.

## 10.3. Análisis de rendimiento

Las comparaciones de rendimiento deberán controlar, cuando sean relevantes, las diferencias en hardware, dependencias, datos, compilación, configuración, carga y método de medición.

Los resultados deberán informar tanto de la medida principal como de su variabilidad o incertidumbre cuando esta afecte la interpretación.

No se declarará una mejora tecnológica a partir de una diferencia de rendimiento aislada sin examinar la validez de la comparación y sus costes asociados.

## 10.4. Resultados inconclusos

Un experimento que no discrimina entre hipótesis no debe presentarse como confirmación de la hipótesis preferida.

Ante resultados inconclusos, el informe deberá indicar si:

- el instrumento carecía de sensibilidad;
- la muestra o el número de réplicas fue insuficiente;
- existieron factores de confusión;
- la medición fue defectuosa;
- las hipótesis no estaban adecuadamente formuladas;
- la pregunta excedía la capacidad del método;
- la evidencia fue contradictoria.

La siguiente acción deberá elegirse según el valor esperado de información adicional y el coste de obtenerla.



---



# 11. Evaluación de evidencia y falsación

## 11.1. Evaluación de afirmaciones

Cada afirmación relevante deberá evaluarse por separado. La evidencia que respalda una propiedad no se utilizará automáticamente para justificar otras propiedades del mismo candidato.

Por ejemplo, superar pruebas de corrección funcional no demuestra rendimiento competitivo, robustez frente a perturbaciones ni transferencia a un dominio nuevo.

La evaluación deberá identificar:

- afirmación examinada;
- evidencia favorable;
- evidencia contraria;
- evidencia ambigua;
- calidad de los instrumentos;
- independencia entre fuentes;
- condiciones de validez;
- limitaciones;
- conclusión permitida.

## 11.2. Dimensiones de la evidencia

La evidencia se evaluará mediante dimensiones separadas:

**Dirección**

- favorable;
- contraria;
- neutral;
- ambigua.

**Calidad metodológica**

- validez del diseño;
- calidad de la medición;
- integridad de los datos;
- reproducibilidad;
- control de factores de confusión.

**Independencia**

- independencia de los datos;
- independencia de la implementación;
- independencia del método;
- independencia de la fuente de evidencia;
- independencia de las condiciones experimentales.

**Suficiencia**

- suficiente para la decisión definida;
- insuficiente;
- contradictoria;
- no evaluable.

No se utilizará el número de resultados como sustituto de la calidad o independencia. Varias ejecuciones que comparten el mismo defecto metodológico pueden repetir el mismo error sin proporcionar confirmación independiente.

## 11.3. Falsación operacional

Toda afirmación importante DEBERÍA disponer de condiciones explícitas que la debiliten, refuten o delimiten.

La investigación deberá buscar pruebas capaces de discriminar entre explicaciones alternativas, incluyendo casos adversos y condiciones límite cuando sean pertinentes.

La ausencia de refutación no equivale a demostración universal. Una afirmación puede quedar respaldada dentro de un dominio concreto sin haber sido validada fuera de él.

## 11.4. Confianza y alcance

Cuando se empleen categorías de confianza, deberán estar definidas para la clase de afirmación y decisión correspondiente.

No se asignará una puntuación única de confianza a un candidato si esta mezcla dimensiones distintas como corrección, rendimiento, generalización y calidad de implementación.

Las conclusiones deberán especificar el dominio evaluado y evitar expresiones universales cuando la evidencia solo cubra condiciones limitadas.



---



# 12. Generalización y transferencia

## 12.1. Dominio de validez

Toda afirmación experimental deberá distinguir entre:

- condiciones probadas;
- condiciones razonablemente cubiertas por el diseño;
- condiciones no examinadas;
- condiciones en las que se espera que la afirmación falle;
- extrapolaciones todavía no verificadas.

El hecho de que un algoritmo funcione en una familia de casos no demuestra que funcione en todos los casos de la misma categoría nominal.

## 12.2. Validación de transferencia

La transferencia de un resultado o activo a un contexto nuevo deberá considerar:

1. semejanzas relevantes entre el contexto original y el nuevo;
2. diferencias en entradas, estados y condiciones;
3. supuestos que podrían dejar de cumplirse;
4. dependencias de la implementación;
5. posibles cambios en las métricas o criterios de éxito;
6. pruebas mínimas necesarias para verificar la transferencia.

La transferencia puede justificar una nueva hipótesis, no necesariamente una conclusión confirmada.

## 12.3. Evidencia de transferencia

El sistema deberá distinguir entre:

- **transferencia propuesta:** se identifica una aplicación potencial;
- **transferencia ensayada:** el activo se utiliza en el nuevo contexto;
- **transferencia verificada:** se satisfacen los criterios de validez definidos;
- **transferencia fallida:** el activo no cumple los criterios bajo las condiciones evaluadas.

Los resultados negativos de transferencia también deberán conservarse. Permiten delimitar el dominio de validez y evitan repetir adaptaciones improductivas.



---



# 13. Decisiones de ingeniería y puertas de control

## 13.1. Clasificación de decisiones

Toda investigación formal deberá cerrarse con una decisión documentada o con una declaración explícita de por qué permanece abierta.

Las categorías son:

| **Decisión**                              | **Significado**                                                                                       |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Continuar**                             | La evidencia justifica invertir en la siguiente etapa.                                                |
| **Corregir**                              | Se identificó un defecto modificable y se autoriza una nueva versión.                                 |
| **Ampliar investigación**                 | Existe una incertidumbre relevante que requiere nuevas pruebas.                                       |
| **Validar**                               | Se autoriza comprobar una propiedad o requisito mediante un procedimiento definido.                   |
| **Transferir**                            | Se autoriza aplicar el conocimiento o activo a otro contexto, sujeto a las verificaciones requeridas. |
| **Archivar por prioridad**                | El trabajo se suspende por asignación de recursos, sin declarar refutada su hipótesis técnica.        |
| **Suspender por limitación instrumental** | La capacidad de evaluación disponible no permite una conclusión suficiente.                           |
| **Descartar por incumplimiento**          | El candidato no satisface un requisito obligatorio demostrado y aplicable.                            |
| **Descartar por evidencia contraria**     | La evidencia contradice una hipótesis o ventaja que justificaba el desarrollo.                        |
| **Cerrar como inconcluso**                | La investigación no resuelve la pregunta dentro del alcance y presupuesto aprobados.                  |

Estas categorías no deben colapsarse en una etiqueta binaria de «aprobado» o «rechazado». Las razones del cierre tienen implicaciones distintas para la inversión futura y el conocimiento institucional.

## 13.2. Puertas de decisión

Las siguientes puertas constituyen un marco de control recomendado. No son una secuencia de certificaciones obligatoria para todos los candidatos.

**G0 — Relevancia de investigación**

¿Existe una pregunta suficientemente importante y una decisión identificable que justifique investigar?

**G1 — Viabilidad**

¿Puede el candidato implementarse, ejecutarse o analizarse de forma que permita obtener evidencia pertinente?

**G2 — Diferencial**

¿Existe evidencia de una ventaja, propiedad o capacidad relevante frente a la referencia adecuada?

**G3 — Fiabilidad**

¿Los resultados son reproducibles y suficientemente sólidos para el uso previsto?

**G4 — Transferencia**

¿La propiedad o ventaja se conserva bajo las condiciones adicionales relevantes?

**G5 — Inversión y despliegue**

¿El beneficio esperado justifica los costes de implementación, mantenimiento, integración y riesgo?

Una puerta puede cerrarse con una decisión negativa sin invalidar el conocimiento obtenido. La investigación debe conservar tanto la razón de la decisión como los límites de la evidencia.

## 13.3. Decisión bajo presupuesto limitado

Cuando no sea viable resolver todas las incertidumbres, el laboratorio deberá priorizar las que tengan mayor probabilidad de cambiar una decisión relevante.

El cierre por presupuesto no equivale a refutación. La documentación deberá indicar qué se sabe, qué no se sabe, qué evidencia faltó y qué coste tendría obtenerla.

El coste ya invertido no justifica continuar automáticamente. Del mismo modo, una investigación no deberá cerrarse solo porque ha consumido el presupuesto inicialmente previsto si existe una razón excepcional y documentada para revisar la asignación.



---



# 14. Sistema de conocimiento institucional

## 14.1. Objetivo

El sistema de conocimiento deberá permitir recuperar resultados, métodos, decisiones y limitaciones de investigaciones anteriores para reducir la duplicación de trabajo y mejorar las decisiones futuras.

No será un archivo documental pasivo ni un repositorio de conclusiones descontextualizadas.

## 14.2. Modelo mínimo de relaciones

El sistema deberá poder representar, como mínimo, las relaciones siguientes:

- un objeto de investigación tiene versiones;
- una pregunta se refiere a uno o más objetos;
- un protocolo tiene versiones;
- un diseño combina un objeto, una pregunta y un protocolo;
- un diseño contiene una o más ejecuciones;
- una ejecución produce observaciones;
- un análisis transforma observaciones en resultados;
- una evidencia respalda o contradice una afirmación;
- una decisión responde a una pregunta y utiliza evidencia;
- una decisión puede autorizar o detener el desarrollo de un activo;
- un activo puede reutilizarse en otras investigaciones;
- una transferencia genera nuevas obligaciones de validación.

Estas relaciones constituyen el modelo semántico mínimo. No obligan a crear una tabla, servicio o archivo independiente para cada entidad desde el primer día.

## 14.3. Registro de conocimiento

Cada afirmación relevante deberá registrar:

- enunciado;
- objeto y versión a los que se refiere;
- dominio de validez;
- evidencia asociada;
- evidencia contraria conocida;
- método de obtención;
- fecha y versión documental;
- estado de validación;
- limitaciones;
- decisiones que dependen de ella;
- condiciones que justificarían su revisión.

El estado de una afirmación deberá diferenciar entre propuesta, examinada, respaldada dentro de un dominio, refutada bajo condiciones especificadas y pendiente de revisión.

Una afirmación histórica no se considerará válida por el simple hecho de estar archivada.

## 14.4. Gestión del conocimiento histórico

La recuperación del corpus histórico se realizará de forma selectiva:

1. inventariar documentos y artefactos existentes;
2. identificar objetos, proyectos y decisiones relacionados;
3. clasificar su procedencia y estado de validación;
4. detectar resultados, protocolos y herramientas potencialmente reutilizables;
5. normalizar los elementos relevantes para investigaciones activas;
6. vincular las nuevas investigaciones con los antecedentes pertinentes;
7. conservar explícitamente los elementos que no hayan podido validarse.

No se requiere migrar todo el historial antes de comenzar a operar. La prioridad será recuperar aquello que pueda reducir costes, evitar errores repetidos o modificar una decisión en curso.

## 14.5. Recuperación orientada a investigación

La recuperación deberá responder preguntas como:

- ¿Qué pruebas han detectado fallos de esta clase?
- ¿Qué protocolos son compatibles con este tipo de candidato?
- ¿Qué afirmaciones dependen de una hipótesis ahora cuestionada?
- ¿Qué resultados negativos existen para este mecanismo?
- ¿Qué cambios de implementación produjeron regresiones?
- ¿Qué activos se han transferido con éxito?
- ¿Qué investigaciones utilizaron condiciones comparables?

La búsqueda no deberá depender exclusivamente de nombres de archivos o coincidencias textuales. Cuando la infraestructura lo permita, utilizará metadatos semánticos y relaciones entre objetos.



---



# 15. Automatización del proceso de investigación

## 15.1. Principio de automatización

La automatización tiene como objetivo reducir trabajo repetitivo, errores de procedimiento y tiempo hasta una decisión fiable.

No constituye un objetivo independiente ni una justificación para construir infraestructura adicional.

Se automatizarán preferentemente las actividades que cumplan una o varias de estas condiciones:

- repetición frecuente;
- procedimiento estable;
- criterios de entrada y salida explícitos;
- coste manual relevante;
- riesgo de error humano repetitivo;
- posibilidad de verificar el resultado automático;
- beneficio potencial en varias investigaciones.

## 15.2. Pipeline operacional

El pipeline objetivo será:

**Candidato → declaración de capacidades → selección de protocolos compatibles → diseño de campaña → ejecución → análisis → decisión → integración de conocimiento.**

El pipeline deberá permitir intervención humana cuando:

- las capacidades estén insuficientemente especificadas;
- la compatibilidad de un protocolo sea dudosa;
- las hipótesis sean ambiguas;
- la evidencia sea contradictoria;
- exista un conflicto entre especificaciones;
- una decisión tenga consecuencias que requieran autorización explícita.

## 15.3. Automatización progresiva

La automatización deberá avanzar por etapas:

**Etapa 1 — Ejecución manual estructurada.** El procedimiento está definido y registra sus resultados, aunque algunas operaciones sean manuales.

**Etapa 2 — Ejecución asistida.** Herramientas reutilizables preparan configuraciones, validan entradas y generan registros.

**Etapa 3 — Orquestación.** El sistema selecciona y ejecuta procedimientos autorizados según reglas explícitas.

**Etapa 4 — Selección adaptativa controlada.** El sistema puede proponer pruebas posteriores según resultados previos, manteniendo registro de la política de selección y de las decisiones automáticas.

**Etapa 5 — Optimización del proceso.** El laboratorio compara el coste y el valor informativo de sus procedimientos y mejora su asignación de recursos.

Cada etapa deberá demostrar utilidad antes de justificar la siguiente. No se asumirá que un sistema completamente automatizado es superior a uno parcialmente automatizado.

## 15.4. Control de cambios metodológicos

Una automatización no deberá modificar silenciosamente el protocolo, las métricas o los criterios de decisión.

Los cambios de procedimiento deberán quedar versionados y ser identificables en cada ejecución.

Cuando un sistema seleccione automáticamente una prueba, deberá registrar la regla de selección, las alternativas consideradas cuando estén disponibles y las razones por las que el instrumento elegido se consideró compatible.



---



# 16. Mejora continua del laboratorio

## 16.1. Objeto de mejora

El laboratorio es también un objeto de investigación. Sus protocolos, instrumentos, sistemas de registro y métodos de análisis deberán evaluarse mediante evidencia.

Las mejoras podrán dirigirse a:

- reducir el coste de caracterización;
- disminuir el tiempo de preparación;
- aumentar la capacidad de detección;
- reducir falsos positivos o falsos negativos;
- mejorar la reproducibilidad;
- aumentar la reutilización de protocolos;
- reducir el tiempo de recuperación de antecedentes;
- mejorar la calidad de las decisiones;
- ampliar la capacidad de transferencia.

## 16.2. Ciclo de mejora

Toda propuesta de mejora relevante deberá identificar:

1. problema operacional observado;
2. línea base;
3. causa propuesta, si se conoce;
4. intervención;
5. indicador afectado;
6. criterio de éxito;
7. posibles efectos adversos;
8. método de evaluación;
9. decisión posterior.

Una mejora no se considerará validada porque el nuevo procedimiento parezca más elegante, contenga más automatización o reduzca una medida aislada.

Deberá evaluarse si mejora el resultado previsto sin deteriorar otras propiedades importantes.

## 16.3. Experimentos sobre el laboratorio

Cuando resulte pertinente, se realizarán comparaciones entre procedimientos alternativos utilizando casos representativos.

Por ejemplo, el laboratorio podrá comparar:

- caracterización manual frente a caracterización asistida;
- protocolos genéricos frente a pruebas adaptadas;
- análisis por resúmenes frente a análisis de trazas;
- distintas políticas de selección de pruebas;
- distintos formatos de registro y recuperación.

Estas comparaciones deberán medir el coste total del proceso y la calidad de las decisiones, no solo el tiempo de ejecución.



---



# 17. Métricas operacionales y evaluación económica

## 17.1. Principio

El laboratorio deberá medir si su infraestructura mejora la producción de conocimiento y tecnología útil. Los indicadores serán instrumentos de dirección, no objetivos que deban maximizarse de forma aislada.

## 17.2. Indicadores principales

| **Indicador**                              | **Definición operativa**                                                                                              |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| **Coste de caracterización**               | Recursos consumidos desde la admisión hasta disponer de información suficiente para decidir la siguiente etapa.       |
| **Tiempo hasta decisión**                  | Tiempo transcurrido desde la formulación de una pregunta hasta una decisión documentada.                              |
| **Coste por pregunta resuelta**            | Recursos consumidos por preguntas cerradas con evidencia suficiente para la decisión definida.                        |
| **Tasa de reutilización de protocolos**    | Proporción de diseños elegibles que reutilizan protocolos existentes sin recrearlos innecesariamente.                 |
| **Coste de adaptación**                    | Recursos requeridos para adecuar un activo existente a un nuevo candidato o contexto.                                 |
| **Reproducibilidad observada**             | Proporción de resultados sometidos a reproducción que cumplen los criterios de compatibilidad establecidos.           |
| **Tasa de regresiones detectadas**         | Frecuencia con la que las pruebas identifican fallos introducidos por cambios respecto de una referencia.             |
| **Valor decisional**                       | Grado en que la evidencia obtenida modifica, confirma justificadamente o delimita una decisión relevante.             |
| **Transferencia verificada**               | Número o proporción de aplicaciones que satisfacen los criterios de transferencia definidos.                          |
| **Reutilización efectiva de conocimiento** | Casos en los que un antecedente recuperado reduce trabajo, evita un error o cambia una decisión de forma verificable. |

Los indicadores deberán definirse de forma precisa antes de utilizarlos para comparar periodos. Los denominadores, exclusiones, unidades y condiciones de medición deben ser estables o quedar documentados.

## 17.3. Indicadores de protección

Para evitar optimizaciones perversas, los indicadores de eficiencia deberán acompañarse de medidas de calidad.

Ejemplos:

- reducir el tiempo hasta decisión sin aumentar los errores de clasificación;
- aumentar la reutilización sin degradar la validez de los protocolos;
- reducir el coste de las pruebas sin perder capacidad para detectar fallos relevantes;
- aumentar el número de candidatos evaluados sin elevar de manera inaceptable las decisiones incorrectas;
- aumentar la automatización sin reducir la trazabilidad.

No se utilizará la tasa de descarte como indicador aislado de eficacia. Una tasa elevada puede reflejar una buena selección de candidatos, una mala selección inicial o un proceso excesivamente propenso a falsos negativos.

## 17.4. Línea base

Antes de afirmar que una nueva infraestructura mejora la productividad, el laboratorio deberá medir el proceso de referencia en una muestra pertinente.

Las comparaciones deberán documentar diferencias de alcance, complejidad y recursos. No se atribuirá una mejora a la infraestructura cuando los cambios puedan explicarse por diferencias sustanciales en los candidatos o en las preguntas estudiadas.



---



# 18. Gestión de riesgos y desviaciones

## 18.1. Riesgos metodológicos

El sistema deberá vigilar, como mínimo, los siguientes riesgos:

- **Falsa generalidad:** extrapolar resultados más allá de las condiciones probadas.
- **Sobreajuste metodológico:** diseñar protocolos que favorecen a un candidato o confirman una expectativa.
- **Falso negativo:** descartar una tecnología potencialmente útil por limitaciones del instrumento o un diseño inadecuado.
- **Falso positivo:** declarar una propiedad que no está respaldada por la evidencia.
- **Confusión causal:** interpretar una asociación o una divergencia como explicación causal sin intervención suficiente.
- **Fragmentación del conocimiento:** conservar resultados sin relaciones, procedencia o condiciones de validez.
- **Sobreingeniería:** construir infraestructura cuyo coste excede su utilidad operacional.
- **Automatización opaca:** producir decisiones que no pueden reconstruirse o auditarse.
- **Dependencia de una referencia defectuosa:** comparar candidatos contra un sistema que también contiene errores.
- **Contaminación experimental:** alterar inadvertidamente el objeto, el entorno o los datos mediante la instrumentación.
- **Cierre prematuro:** declarar resuelta una pregunta cuando persisten incertidumbres que podrían cambiar la decisión.
- **Continuación por coste hundido:** invertir recursos adicionales porque ya se ha invertido mucho, en lugar de por el valor esperado de la investigación.

## 18.2. Registro de desviaciones

Toda desviación material de un protocolo aprobado deberá registrar:

- requisito o procedimiento afectado;
- motivo;
- momento de detección;
- ejecuciones afectadas;
- posible impacto sobre los resultados;
- autorización, cuando corresponda;
- medidas correctivas;
- necesidad de repetir o invalidar ejecuciones.

Una ejecución afectada por una desviación no se eliminará del historial. Su estado deberá reflejar si sigue siendo válida, si requiere revisión o si no puede utilizarse para sustentar la conclusión original.

## 18.3. Incidentes de integridad

Cuando existan indicios de corrupción de datos, modificación no autorizada, pérdida de trazabilidad o discrepancia entre lo ejecutado y lo registrado, la investigación deberá suspender las conclusiones afectadas hasta determinar el alcance del incidente.

No se reconstruirán resultados mediante supuestos no documentados para aparentar continuidad.



---



# 19. Control de calidad y auditoría

## 19.1. Revisión previa

Antes de una campaña relevante, se revisarán:

- claridad de la pregunta;
- adecuación del protocolo;
- compatibilidad del candidato;
- criterios de decisión;
- controles y referencias;
- presupuesto;
- reproducibilidad prevista;
- riesgos de sesgo;
- suficiencia del registro;
- condiciones de cierre.

La profundidad de la revisión dependerá de la importancia y el riesgo de la investigación.

## 19.2. Revisión posterior

Al cerrar una investigación, se comprobará:

- si el procedimiento ejecutado corresponde al aprobado;
- si los resultados pueden rastrearse hasta sus datos de origen;
- si las conclusiones respetan el alcance de la evidencia;
- si se han registrado resultados contrarios y ambiguos;
- si la decisión está justificada;
- si existen activos reutilizables;
- si se han documentado las limitaciones;
- si corresponde modificar algún procedimiento.

## 19.3. Estados de conformidad

La documentación y los componentes deberán distinguir explícitamente entre:

- **ESPECIFICADO:** existe un requisito o comportamiento definido.
- **IMPLEMENTADO:** existe una implementación que pretende satisfacerlo.
- **VERIFICADO:** se han aplicado procedimientos adecuados y existe evidencia del cumplimiento dentro de su alcance.
- **OBSERVADO:** el comportamiento se ha registrado, sin implicar por sí solo su conformidad.
- **AMBIGUO:** la definición no permite una interpretación inequívoca.
- **NO EVALUADO:** no se ha realizado la evaluación requerida.
- **NO APLICABLE:** el requisito no corresponde al objeto o contexto evaluado, con justificación.

No se inferirá el estado VERIFICADO a partir de la mera existencia de código, documentación o pruebas diseñadas.



---



# 20. Contratos mínimos de información

El laboratorio deberá implementar esquemas de información versionados. Los siguientes campos representan un contrato semántico mínimo, no una exigencia de formato o tecnología concreta.

## 20.1. Registro de candidato

-

```
candidate_id
```

1.

```
name
```

1.

```
version
```

1.

```
specification_reference
```

1.

```
implementation_reference
```

1.

```
capabilities
```

1.

```
constraints
```

1.

```
known_dependencies
```

1.

```
claims
```

1.

```
unknowns
```

1.

```
admission_status
```

## 20.2. Registro de pregunta

-

```
question_id
```

1.

```
research_object_id
```

1.

```
question_statement
```

1.

```
decision_relevance
```

1.

```
hypotheses
```

1.

```
acceptance_or_refutation_criteria
```

1.

```
known_uncertainties
```

1.

```
budget
```

1.

```
status
```

## 20.3. Registro de protocolo

-

```
protocol_id
```

1.

```
version
```

1.

```
purpose
```

1.

```
compatibility_conditions
```

1.

```
preconditions
```

1.

```
procedure
```

1.

```
variables
```

1.

```
measurements
```

1.

```
termination_conditions
```

1.

```
limitations
```

1.

```
validation_status
```

## 20.4. Registro de diseño y ejecución

El diseño deberá identificar el candidato, la pregunta, el protocolo, la configuración, las variables y el plan de ejecución.

Cada ejecución deberá identificar el diseño, las condiciones reales de ejecución, las versiones de dependencias, los datos registrados, los errores, el estado final y las referencias a los resultados.

La separación entre diseño y ejecución es obligatoria para conservar la relación entre una campaña experimental y sus réplicas.

## 20.5. Registro de evidencia

-

```
evidence_id
```

1.

```
claim_id
```

1.

```
source_run_ids
```

1.

```
evidence_direction
```

1.

```
method_quality
```

1.

```
independence_dimensions
```

1.

```
sufficiency_status
```

1.

```
scope
```

1.

```
limitations
```

1.

```
analysis_reference
```

## 20.6. Registro de decisión

-

```
decision_id
```

1.

```
question_id
```

1.

```
decision_type
```

1.

```
supporting_evidence
```

1.

```
contrary_evidence
```

1.

```
rationale
```

1.

```
known_uncertainties
```

1.

```
authorized_scope
```

1.

```
follow_up_conditions
```

1.

```
review_status
```

## 20.7. Registro de activo reutilizable

-

```
asset_id
```

1.

```
asset_type
```

1.

```
version
```

1.

```
originating_research
```

1.

```
intended_use
```

1.

```
compatibility_conditions
```

1.

```
known_limitations
```

1.

```
validation_status
```

1.

```
transfer_history
```

1.

```
maintenance_requirements
```

Los esquemas deberán versionarse. La evolución del modelo de información no deberá alterar retroactivamente el significado de registros históricos sin dejar constancia de la transformación.



---



# 21. Secuencia de implantación del Playbook

El Playbook deberá implantarse de forma incremental, verificando su utilidad en investigaciones reales antes de ampliar la infraestructura.

## Fase 1. Contratos operacionales mínimos

**Objetivo:** disponer de un ciclo formal ejecutable de principio a fin.

Entregables:

- taxonomía aprobada;
- registro de candidato;
- contrato de pregunta;
- protocolo versionado;
- registro de diseño y ejecución;
- esquema de resultados y decisiones;
- procedimiento de cierre.

**Criterio de salida:** una investigación real puede recorrerse desde la admisión hasta la decisión con trazabilidad suficiente.

## Fase 2. Reutilización de protocolos

**Objetivo:** reducir la recreación de pruebas para candidatos sucesivos.

Entregables:

- catálogo inicial de protocolos;
- fichas de compatibilidad;
- mecanismo de selección;
- procedimiento de adaptación;
- control de versiones;
- registro de resultados de reutilización.

**Criterio de salida:** un segundo candidato pertinente puede evaluarse reutilizando al menos parte de la infraestructura anterior y midiendo el coste de adaptación.

## Fase 3. Reproducibilidad y análisis

**Objetivo:** garantizar que las conclusiones puedan reconstruirse y auditarse.

Entregables:

- trazabilidad de datos;
- mecanismos de reproducción adecuados al instrumento;
- análisis versionado;
- comparación entre ejecuciones;
- registro de evidencia favorable, contraria y ambigua.

**Criterio de salida:** los resultados de una investigación pueden verificarse sin depender exclusivamente de la memoria o interpretación de quien la ejecutó.

## Fase 4. Sistema de conocimiento

**Objetivo:** convertir resultados y decisiones en recursos recuperables.

Entregables:

- relaciones entre preguntas, protocolos, ejecuciones y afirmaciones;
- búsqueda de antecedentes;
- catálogo de activos;
- registro de resultados negativos;
- procedimiento de transferencia.

**Criterio de salida:** una nueva investigación puede recuperar antecedentes relevantes y demostrar si estos reducen trabajo o cambian una decisión.

## Fase 5. Orquestación y mejora

**Objetivo:** automatizar operaciones repetitivas y optimizar la asignación de recursos.

Entregables:

- orquestación de protocolos;
- validación automática de entradas;
- generación de informes;
- indicadores operacionales;
- experimentos comparativos sobre métodos de investigación.

**Criterio de salida:** la automatización demuestra una mejora verificable de coste, tiempo, calidad o capacidad de investigación sin degradar la trazabilidad.

Las fases pueden solaparse cuando exista una justificación técnica. Ninguna fase debe considerarse completada por la mera entrega de documentación o código: requiere evidencia de funcionamiento dentro del alcance declarado.



---



# 22. Criterios de aceptación del Playbook

La versión operacional inicial podrá considerarse apta para uso cuando se demuestre que:

1. Los términos fundamentales tienen definiciones consistentes.
2. Las preguntas de investigación están vinculadas a decisiones o necesidades de conocimiento explícitas.
3. Los protocolos declaran su propósito, compatibilidad y limitaciones.
4. Las ejecuciones quedan vinculadas a versiones, configuraciones y condiciones identificables.
5. Los resultados pueden rastrearse hasta sus fuentes.
6. La evidencia contraria y los resultados inconclusos pueden registrarse sin perder su significado.
7. Las decisiones distinguen entre refutación, incumplimiento, falta de evidencia y priorización de recursos.
8. Los activos reutilizables conservan sus condiciones de aplicación.
9. Las modificaciones metodológicas quedan versionadas.
10. Existe un procedimiento de cierre que incorpora conocimiento y evalúa oportunidades de mejora.
11. El ciclo ha sido probado con una investigación real.
12. Se han identificado los costes y limitaciones del propio procedimiento.

La aceptación inicial no implica que todas las capacidades estén automatizadas ni que todos los protocolos estén validados. Implica que existe un marco operacional coherente, ejecutable y evaluable.



---



# 23. Principio de cierre operacional

El laboratorio deberá considerar una investigación cerrada cuando la decisión correspondiente esté documentada, los resultados y sus limitaciones estén preservados, y las obligaciones pendientes estén identificadas.

El cierre no exige que todas las incertidumbres hayan sido resueltas. Exige que se determine qué se ha resuelto, qué permanece desconocido, qué decisión se adopta y qué condiciones justificarían reabrir el trabajo.

La mejora del laboratorio deberá basarse en evidencia obtenida durante su operación. No se dará por supuesto que un nuevo procedimiento, una taxonomía más extensa o una automatización adicional incrementan la capacidad tecnológica por el simple hecho de existir.

**Criterio rector:** toda inversión operacional deberá justificarse por su contribución a la calidad de la evidencia, la velocidad de decisión, la reducción de costes repetitivos, la fiabilidad de la tecnología o la acumulación verificable de conocimiento reutilizable.

El objetivo final no es producir más experimentos de manera aislada. Es construir un sistema capaz de estudiar más candidatos, con mayor profundidad cuando sea necesario, tomar mejores decisiones y convertir una proporción creciente del trabajo realizado en capacidad tecnológica disponible para los ciclos siguientes.