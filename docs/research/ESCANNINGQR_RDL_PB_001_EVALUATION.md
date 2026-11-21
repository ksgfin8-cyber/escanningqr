# EQ-R01 · Evaluación tecnológica, diferencial y composicional de EscanningQR

**Registro v1 · 21 de noviembre de 2026 · Dictamen de investigación**

## 1. Identificación, alcance y procedencia

| Fuente | Identidad y función |
| --- | --- |
| EscanningQR, candidato EQ | `ksgfin8-cyber/escanningqr@b81c173f5325a382bb15ba29d246db7b9fdf22ef`. Siete archivos de producto e instrumentos. |
| RDL-PB-001 v0.1 | [Texto operacional](../program/RDL-PB-001_v0.1_original_propuesta.md), incorporado en `3ab62622f2e6022a67077f9d6f0cd3ce9a348261`. Marco de la investigación. El cambio de árbol entre ambos commits solo agrega el Playbook. |
| Almuerzos Ecuador, referencia AE | `ksgfin8-cyber/almuerzos-ecuador@5a19920ab0a8a6169e4b725b308506d7d93c75f6`, 26 de febrero. Se usa para comparar los cuatro archivos de producto. |
| Documentos retrospectivos de AE | `invariantes.md` en `9c0ddf6ed600a4d0917114aed198109a92b36883` (14 de octubre), `CRITERIO_EXTENSION.md` en `30e603dedf6473b6e649924c562d9991ddb556f0` (10 de noviembre) y `docs/research/almuerzos-ecuador-rdl-pb-001.md` en `851e36ffc70ee9f76cfaa8115d5d4e771d0fbaa6` (21 de noviembre). Disponibles en el árbol `af7cf3284d83319ce7edf99cc4db02222ce649f1`. AE-R01 evalúa `d9618be89926e805038ec514326245443cce8707`, con los mismos cuatro archivos de producto que la referencia de febrero. |

Las fechas son las de autor registradas por Git. AE tiene código desde el 13 de enero (`d0cea17`) y la versión de su motor usada aquí data del 16 de enero (`ca4a8ef`). EQ comienza con el CLI (`b35b0d6`) y el 19 de febrero incorpora motor, interfaz, menú y validación HTML (`eb21a52`), ya con modo InHouse en el motor. El QR inicial (`bc7b521`) apuntaba a la página raíz sin modo. `710b549` incorpora estilos y `1370af8` añade `?modo=inhouse` el 22 de febrero. Las series de menú del 23 al 26 tienen commits separados y terminan con el mismo catálogo. La historia alcanzable de las dos revisiones tiene raíces distintas y no comparte commits. La precedencia y las coincidencias de implementación sostienen una derivación técnica de alta confianza. El mecanismo de copia, la autoría del diseño previo y el orden de trabajo fuera de Git quedan indeterminados.

El creador declaró la intención de organizar A–G como piezas formalizables y ampliables por composición. Esa intención motivó Q4. Los rótulos y dependencias en el código de febrero documentan la arquitectura observable. Los documentos de octubre y noviembre aportan vocabulario y criterios de contraste retrospectivo. La evaluación se limita a los árboles fijados, un reloj controlado y efectos simulados, sin pedidos reales ni cambios a los productos.

## 2. Dictamen ejecutivo

EscanningQR especializa el mismo flujo de pedidos de almuerzo para un acceso presencial. Una URL selecciona una política que elimina el despacho estimado, ajusta los puntos cuando el mercado está abierto y marca el mensaje para el receptor. El QR automatiza la entrada por esa URL desde un lector externo. El producto conserva la selección, el reloj y las restricciones de atención de AE, incluida la dependencia del próximo despacho para declarar disponibilidad aun en InHouse.

Con catálogo y reloj iguales, se verificaron igualdad de evaluación y mensaje entre AE y EQ normal durante 10 080 minutos y con dos pedidos. La especialización es localizable en E, F y G y conserva el código de A–D bajo la normalización descrita. Esto respalda la extensión por parámetros y contratos de datos en esta familia. La facilidad de incorporar políticas nuevas, la composición arbitraria y el ahorro de ingeniería siguen sin medirse. La restricción de despacho a las 14:00, la retención de puntos base durante fines de semana y el significado de `ENVIADO` requieren una decisión de producto si se pretende otro comportamiento.

## 3. Caracterización tecnológica

Sitio estático de scripts clásicos, HTML y CSS, sin compilación ni backend propio. Entradas de producto: identificadores del catálogo, gestos con cantidades, extras binarios, fecha civil del dispositivo, configuración local y consulta de URL. Salidas: resumen y estado de atención en DOM, texto formateado y solicitud de apertura de un enlace externo. El pedido vive en memoria. El número de destino se lee de almacenamiento local y puede persistirse por un gesto de configuración. No existe adaptación basada en experiencia ni registro local de entregas. El generador independiente usa qrcodejs 1.0.0 desde un CDN, una URL fija de GitHub Pages y el diálogo de impresión del navegador ([generadorqr.html](../../generadorqr.html#L6), [configuración del QR](../../generadorqr.html#L42)).

Con `URLSearchParams.get('modo')`, G usa el primer valor decodificado y reconoce exactamente `inhouse`. La consulta es una señal de presentación y política, accesible también manualmente. La aplicación carece de verificación del escaneo, presencia física o identidad. Para el flujo completo hacen falta un navegador con almacenamiento disponible, un reloj local razonable, un destino de despliegue que atienda la URL, la biblioteca para generar el QR y el canal externo para completar la comunicación. El formulario de pedidos carece de dependencia de qrcodejs durante su propia carga. [Captura y arranque](../../sistema.js#L286).

## 4. Matriz diferencial frente a Almuerzos Ecuador

Comparación P0 mediante `git show`, `git log` y `diff -u --strip-trailing-cr`. Los archivos compartidos tienen blobs distintos. La comparación de texto normaliza CRLF/LF y conserva los demás caracteres.

| Pieza | Diferencia observada | Alcance |
| --- | --- | --- |
| A · `estilos.css` | Igual después de normalizar finales de línea. | Presentación reutilizada. |
| B · `index.html` | Dos comentarios adicionales sobre desconocimiento del modo. Código restante igual. | Cambian valores presentados por datos de E. El despacho puede desaparecer y los puntos cambiar sin ramificación de B por modalidad. |
| C · `sistema.js:16–54` | Mismos cuerpos y firmas, incluida la creación de pedido vacío. | Los gestos mantienen su representación y semántica de lista. |
| D · `sistema.js:57–119` | Comentario adicional, método idéntico. | Misma fuente de reloj, franjas, puntos base y tabla de despachos. |
| E · `sistema.js:130–186` | `evaluar(p,t)` pasa a `evaluar(p,t,k={modo:'normal'})`. Omite despacho InHouse y fija tres puntos en abierto. | Conserva claves, ejecutabilidad, motivo y estado de mercado para ambos modos. |
| F · `sistema.js:200–254` | `generarMensaje(p,e,t,m)` agrega quinto argumento opcional. Etiqueta InHouse después del título y suprime la nota horaria cuando no hay despacho en esa modalidad. | Formato normal preservado. La sección de despacho depende de `e.despachoAsignado`, de modo que un E normal combinado con un F InHouse produce etiqueta y despacho juntos. |
| G · `sistema.js:266–484` | Captura, guarda y propaga el contexto al actualizar y al enviar. | Conserva gestos, tick, guardado y mecanismo de apertura. Agrega una dependencia de `window.location.search` al arrancar, incluso para el modo normal. |
| Catálogo · `menu.js` | Igual en los commits finales tras normalizar finales de línea. | Coinciden cinco bases y dos extras. La evolución intermedia del menú es independiente de la política InHouse. |
| QR y validaciones | `generadorqr.html`, `validacion-cli.js` y `validacion.html` añadidos en EQ. | Generación e impresión de un acceso fijo y dos instrumentos de comprobación, con distinta fidelidad al producto. |

## 5. Investigación de arquitectura A–G

La ruta habitual es gesto DOM → callback → G → C → D/E → proyección DOM. Al solicitar envío, G vuelve a consultar D/E, aplica la política de aviso y confirmación, llama a F, normaliza dos caracteres y solicita apertura externa. El generador se conecta mediante un contrato de URL, sin importar los scripts del pedido. El cambio recorre tres consumidores concretos: G selecciona el modo, E modifica la evaluación y F modifica el texto. A/B/C/D conservan su implementación ejecutable. La configuración mantiene el acoplamiento heredado de B con `Sistema` y B también consulta a `Pedido`. El catálogo y los bloques se comparten como nombres globales y archivos ordenados por carga. Los límites son responsabilidades observables y convenciones de integración, con escasa protección frente a sustituciones incoherentes. [B y sus callbacks](../../index.html#L325), [evaluación y efectos](../../sistema.js#L372).

| Pregunta | Hipótesis, criterio y decisión que informa |
| --- | --- |
| Q1 · Diferencial | Un modo seleccionable cambia evaluación y mensaje sin cambiar el pedido. Una diferencia reproducible en esos campos respalda el uso como especialización local. P0–P2. |
| Q2 · Conservación | La proyección normal reproduce AE con el mismo catálogo, reloj y entradas válidas. Un caso distinto obliga a revisar compatibilidad. P0–P1. |
| Q3 · Contexto | Captura inicial, propagación coherente y variación acotada; cambios tras un tick, acoplamiento de disponibilidad o combinaciones incompatibles delimitan el contrato. P1–P2. |
| Q4 · Composición | Responsabilidades separables y transformaciones tipables. Una firma incompatible, un estado omitido o un contraejemplo a una ley delimita la formalización utilizable. P0–P2 y derivación §6. |
| Q5 · Instrumentos | La confianza exige ejecutar el objetivo real y detectar fallos pertinentes. Duplicación, oráculos insensibles o falsos positivos condicionan el uso para regresión. P3. |
| Q6 · Transferencia | Fuente compartida y especialización verificables. Para un dominio receptor se requieren criterio, aplicación y coste con comparador. P0–P3 delimitan el punto de partida. |

## 6. Evaluación matemática y epistemológica

**Transición.** Para un modelo discreto del núcleo se puede usar `s=(fase,pedido,contexto,catálogo,destino,última instantánea,última evaluación)`. La entrada distingue arranque, tick, ajuste, extra, reset, configuración y solicitud de envío, con lectura de reloj, resultados de almacenamiento y decisión de confirmación según corresponda. Las salidas incluyen proyección de UI, aviso y solicitud de apertura. Una transición de tipo Mealy `s × i → s' × o` captura trazas con límites definidos. El arranque asíncrono y la confirmación se pueden representar mediante eventos de resultado o fases intermedias. Incluir el navegador completo exige modelar DOM, temporizadores, errores y efectos adicionales; la fase textual de G sola no identifica el estado. La finitud requeriría fijar dominios y equivalencias para cantidades, textos, reloj y estado externo. Aquí resulta defendible un sistema de transición con salidas, sin construir una máquina finita explícita.

**Composición de transformaciones.** Sobre pedidos válidos, con catálogo fijo e identificadores definidos, las operaciones parametrizadas de C se modelan como endofunciones. Las secuencias de gestos forman un monoide libre bajo concatenación si se incluye la secuencia vacía. Su interpretación en endofunciones conserva identidad y composición, con el orden de aplicación especificado. El conjunto de generadores de una sola acción carece de clausura por sí mismo. Reset es idempotente y devuelve vacío cuando se aplica al final; reset seguido de sumar A devuelve A:1. Dos sumas sobre bases distintas pueden dejar el mismo multiconjunto en distinto orden, observable en F. Alternar un extra presente y volver a agregarlo también puede cambiar el orden con varios extras. Por tanto las igualdades de gestos dependen de si se observa la lista, la pertenencia o el mensaje. IC.3 sustenta ausencia de mutación por los métodos; referencias compartidas y objetos sin congelar limitan una lectura de inmutabilidad profunda.

**Compatibilidad.** Para instantáneas producidas por D y entradas ordinarias, E normal sigue las mismas ramas que AE; en F normal los dos saltos de línea iniciales y el resto del texto se conservan. Los argumentos finales por defecto preservan las invocaciones de E/F de AE. Con `k=inhouse`, E conserva la proyección `(ejecutabilidad,motivo,estadoMercado)`; F conserva identidad y cantidad de selección, y especializa etiqueta y texto operativo. Compartir esquema de datos permite sustituir parcialmente componentes. La coherencia exige que E y F reciban el mismo modo y el mismo reloj, y que los IDs de C existan en el catálogo. `null` para el contexto, estados fabricados y catálogos incompletos quedan fuera del contrato de entrada ordinario. La prueba de mezcla E/F exhibe una incompatibilidad semántica que el esquema no detecta.

**Gramática y máquinas.** A–G designa un vocabulario de roles, orden de interacción y tipos de mensajes implícitos. Una gramática formal exigiría definir alfabeto, producciones, objetos generados y reglas de validez; la evidencia soporta diagramas tipados y una semántica de trazas local. Se puede construir una categoría de estados y transiciones según una definición escogida, siempre que dominios y codominios coincidan, haya identidades y clausura. Una composición en serie de máquinas requiere compatibilidad entre la salida y la entrada, estado conjunto y reglas de sincronización; los callbacks y el ciclo G–B necesitan un protocolo de eventos. La asociatividad de la composición de funciones no establece que las piezas de código se sustituyan libremente ni que su combinación preserve propiedades. Las afirmaciones de entropía o información mutua de `invariantes.md` necesitan variables aleatorias, distribuciones y observables. B muestra una proyección de E aunque carezca de acceso directo a sus reglas; ese flujo impide inferir independencia estadística del desacoplamiento de código.

## 7. Protocolos, ejecuciones y resultados

Campaña de inspección y pruebas controladas (§§7–9). Se priorizaron las fronteras que podían cambiar el dictamen y se usó una semana civil íntegra porque recorrer sus minutos es barato. El presupuesto de validación excluyó rendimiento, experiencia de usuario, transacciones externas y pruebas de campo. Criterio de terminación: inventario y diferencias trazables, resultados comparables, contraejemplos localizados y límites registrados. Las ejecuciones del 21 de noviembre de 2026 usaron Linux y Node v24.22.3 con `TZ=America/Guayaquil`, sin semilla por carecer de entradas aleatorias. Git sirve como lector de ambos objetos fijos. Reloj, temporizador, almacenamiento, confirmaciones y apertura se controlan localmente. Los objetos productivos se evalúan sin editar sus archivos. El modo estricto se prueba solo como intervención en memoria y se identifica como tal.

| ID / versión | Diseño y ejecución | Observaciones y alcance |
| --- | --- | --- |
| P0 v1 / R1 | Inventario Git, lectura, comparación normalizada, historia y revisión contractual. | Matriz §4. La igualdad de archivos normalizados y cuerpos aporta evidencia de reutilización. Las historias separadas limitan la atribución histórica. |
| P1 v1 / R1 | Evaluaciones con dos pedidos durante la semana del lunes 19 al domingo 25 de enero de 2026. Caso vacío y B:2 con JUGO. Referencia AE y control EQ normal explícito y por defecto. | Interrumpida el sábado a las 11:00. El oráculo del mensaje esperaba tres por cualquier puntaje positivo. El texto mostró uno y E coincidía con la regla de conservar puntos base en cerrado. La pasada se conserva como evidencia de la discrepancia, sin usarla como barrido completo. |
| P1 v2 / R2 y R3 | Se cambió la aserción de texto para comprobar el valor esperado por la política y verificado antes en E. Dos ejecuciones completas. | 10 080 instantes a un minuto × 2 pedidos, con igualdad de D, E y F normal bajo las condiciones fijadas. En InHouse coincidieron las proyecciones indicadas y se comprobó el mensaje de ambos pedidos. Salidas idénticas byte a byte. |
| P2 v1 / R2 y R3 | Dentro de las mismas ejecuciones, arranque con cinco consultas, callbacks de selección, tick, cancelación y confirmación; almacenamiento denegado, reasignación de contexto, combinación E/F incoherente y generador con dobles de DOM y biblioteca. | Estado inicial LISTO y sin apertura. Arranque denegado entra en ERROR. Los gestos conservan pedido a través del tick y reset seguido de suma da A:1. Confirmación positiva con apertura nula queda en ENVIADO. El constructor QR recibe la URL fija, 300 × 300 y corrección H. Su ausencia causa ReferenceError. El instrumento no mide render físico, lectura óptica ni resolución remota. |
| P3 v1 / R1–R3 | R1, CLI intacto. R2/R3, HTML real evaluado con DOM mínimo y carga de scripts de EQ; réplica con directiva estricta añadida en memoria. | CLI 30/30. HTML intacto 32/34. Los dos objetos quedan congelados y conservan modo. La variante estricta da 34/34. La intervención discrimina fallos del oráculo frente a mutación. |

**Detalle del barrido.** Se observaron 5 095 minutos `FUERA_DE_HORARIO`, 1 200 `ABIERTO_TEMPRANO`, 300 `ABIERTO_NORMAL`, 600 `ABIERTO_TARDIO`, 5 `SIN_DESPACHO` y 2 880 `FIN_DE_SEMANA`. Los recuentos corresponden a minutos, una sola vez por instante. La partición depende del reloj local y la política estática, no de un muestreo de operaciones comerciales.

| Instante civil | Mercado y motivo, ambos modos | Normal: despacho / puntos | InHouse: despacho / puntos |
| --- | --- | --- | --- |
| Lun 06:59 | Cerrado, fuera de horario | — / 0 | — / 0 |
| Lun 07:00 y 10:59 | Abierto temprano | 12:00 / 3 | — / 3 |
| Lun 11:00 y 11:59 | Abierto normal | 12:00 / 1 | — / 3 |
| Lun 12:00 | Abierto tardío | 12:30 / 0 | — / 3 |
| Lun 13:59 | Abierto tardío | 14:00 / 0 | — / 3 |
| Lun 14:00 | Cerrado, sin despacho | — / 0 | — / 0 |
| Lun 14:01 | Cerrado, fuera de horario | — / 0 | — / 0 |
| Sáb 09:00 y 11:00 | Cerrado, fin de semana | — / 3 y 1 | — / 3 y 1 |

A las 14:00 D aún emite franja tardía, pero el despacho exige una hora estrictamente posterior. E evalúa la falta de despacho antes de aplicar la modalidad. El supuesto de disponibilidad compartida es, por tanto, efectivo aunque InHouse no muestre despacho. A las 14:00 cancelar genera solo confirmación. Al aceptar se solicita una apertura hacia la ruta ficticia `/000` y se emite confirmación visual aun si el doble devuelve `null`. InHouse conserva la etiqueta y suprime la nota de fuera de horario en el texto final. El pie del formulario y el estado local describen el intento, cuyo éxito externo queda fuera de alcance. [Prioridad de E](../../sistema.js#L144), [envío de G](../../sistema.js#L400).

**Sensibilidad de los instrumentos.** El [CLI](../../validacion-cli.js#L1) redefine C, D, E y F, fabrica un G reducido y usa entradas propias. Sus comprobaciones muestran las salidas de esa copia y contienen comprobaciones de estructura que pueden pasar aunque el producto real diverja. El resumen tampoco usa un código de salida distinto al detectar fallas. El [HTML](../../validacion.html#L21) carga `menu.js` y `sistema.js`, pero fabrica contextos y evaluaciones, inspecciona propiedades y ejercita principalmente funciones, sin ejecutar la cadena real de captura, propagación y apertura. En el script clásico, reasignar una propiedad congelada en modo no estricto falla silenciosamente. Los casos de las líneas 65–77 toman cualquier ausencia de excepción como mutabilidad. El cambio controlado de directiva y la inspección del valor descartan esa interpretación. El caso cerrado artificial de ambos instrumentos tiene cero puntos base, por lo que no detecta la retención de puntos positivos del fin de semana.

**Independencia y desviaciones.** R2 y R3 repiten código, reloj, datos y método en el mismo entorno. La lectura estática y la ejecución tienen métodos distintos y origen de datos compartido. AE aporta un código de referencia separado con parentesco, no un oráculo independiente de corrección del negocio. La intervención estricta cambia el oráculo, no el producto publicado. La primera falla de P1 se registró, se corrigió únicamente el instrumento con una versión nueva y se repitió la matriz completa. La sustitución de dependencias de navegador es parte del diseño. La lectura e impresión de un QR real, el acceso desde archivo, la navegación móvil, la recepción externa y el comportamiento en otras zonas quedan **NO EVALUADOS**. La evidencia de navegador del informe AE-R01 sirve como antecedente y conserva sus propios límites.

## 8. Invariantes y límites

Las referencias IG numeradas aquí son globales salvo indicación. Los estados se aplican dentro del alcance de §7. Las reglas de `invariantes.md` y el filtro de `CRITERIO_EXTENSION.md` se usan retrospectivamente.

| Afirmación | Evidencia y suficiencia |
| --- | --- |
| IG.1, IC.1–2, IE.1–2 · Tiempo único y pedido atemporal | Favorable. D es el único acceso a Date en el flujo, y E recibe su instantánea. El tick retiene la selección y su referencia. D incluye política de franjas y despachos, lo cual deja **AMBIGUA** la frontera de ID.2 si «hechos» excluye calendarios comerciales. |
| IG.2, IB.1–3 · Estado y callbacks | Se conserva la autoridad de G sobre la selección. La unicidad literal de memoria tiene evidencia contraria heredada: B mantiene referencias de menú y callbacks y estado en DOM, lee configuración global y llama a G para guardarla. El QR mantiene su propio DOM. La lectura restringida a estado de negocio del pedido es compatible con lo observado. |
| IC.3 e ID.3 · Conservación e inmutabilidad | P0 y P1 respaldan transformaciones sin escritura en el pedido anterior y retorno congelado de D. P2 verifica que el objeto de contexto se congela; el campo que apunta a él se puede reasignar y un nuevo arranque lo reconstruye. La estabilidad se restringe al flujo ordinario. |
| IG.4 · Evaluación estructurada | **VERIFICADO** para las ramas ejecutadas. Conserva estados y motivos; `DIFERIDO` carece de transición productiva. `NO_EJECUTABLE` admite un intento con confirmación. La interpretación como veto estricto tiene evidencia contraria. |
| IG.5 e ID.1 · Determinismo | E/F deterministas con instantánea, modo y menú fijados, favorable. Sin modo, el mismo C y D puede producir resultados diferentes. D lee reloj y locale del entorno; carece de pureza referencial si se modela sin entradas externas. |
| IG.6 e IE.3 · Puntos y persuasión | **VERIFICADO** estructuralmente que los puntos no intervienen en ejecutabilidad. La política de tres puntos en abierto, incluida la franja que tenía cero, cambia un estímulo mostrado. La ausencia de efecto persuasivo sobre personas es insuficiente como conclusión sin estudio conductual. |
| IG.7 · Agencia humana | **OBSERVADO** en la ruta probada: arranque y tick sin apertura, pedido vacío con aviso, envío fuera de horario con cancelación efectiva. Los métodos de G se pueden invocar por código; la garantía refiere al flujo de interfaz y no es control de autorización. |
| IF.1–3 · Traducción | F conserva acceso externo nulo y mapea selección y evaluación. Suprime una advertencia mediante contexto y necesita datos compatibles de E. La traducción de selección es verificable, mientras que la fidelidad a toda información operativa depende del contrato que fije el propietario. |
| Extensión y portabilidad | A–D, representación y gesto explícito se conservan. El QR agrega una dependencia de runtime fuera de G en una página propia. Bajo una lectura de portabilidad sin infraestructura externa para todo el producto, la ruta QR es incompatible; para el formulario estático, la dependencia queda fuera de su carga. La ejecución directa desde archivo permanece abierta. |

## 9. Capacidades reutilizables y condiciones de transferencia

| Activo y problema | Evidencia actual | Adaptación y revalidación |
| --- | --- | --- |
| C y catálogo separado para construir una selección | Código compartido y traza conservada en el mismo dominio. | Acordar IDs, cantidades, multiplicidades, orden y tratamiento de entradas inválidas. Probar cierre de transformaciones y fidelidad del mensaje. |
| D/E y política parametrizada | Reutilización de D y especialización de E comprobadas entre AE y EQ. | Separar reloj, zona y política si el receptor tiene feriados, ventanas, horarios distintos o disponibilidad presencial independiente. Probar bordes y proyecciones. |
| G/F y contexto de entrada | Propagación desde una consulta URL a evaluación y traducción. | Definir procedencia, vigencia e identidad del contexto y contratos de datos. Si el receptor exige presencia comprobada, hace falta un mecanismo distinto con evidencia propia. |
| QR como adaptador de entrada | Ensayado el contrato local de parámetros y captura de consulta. | Acordar destino, accesibilidad, mantenimiento del enlace y disponibilidad de biblioteca; escanear una impresión y validar destino solo en un escenario autorizado. |
| Protocolo diferencial con reloj y efectos sustituidos | Método de AE-R01 adaptado y ejecutado en EQ, con cobertura ampliada y control negativo. | Fijar objetivo real, unidad temporal, oráculo de diferencia y punto de efectos. Validar utilidad y coste con un receptor independiente. |

La reutilización de código y la especialización dentro de pedidos de almuerzo están verificadas en los límites de P0–P2. La portabilidad conceptual de roles, mecanismos y procedimiento constituye transferencia **propuesta** para otros dominios (§12.3). El ensayo del método AE-R01 sobre EQ demuestra adaptación en la misma familia; queda por validar en un contexto distinto.

## 10. Evaluación de costes e incertidumbres

P0 contabiliza cuatro archivos compartidos, con cero cambios sustantivos en estilos y menú final, dos líneas de comentarios en la interfaz y 79 líneas añadidas y 20 retiradas en el motor bajo la normalización adoptada. Hay tres archivos propios de EQ, dos de ellos instrumentales. Este recuento aproxima superficie de revisión, con dependencia de decisiones de formato y empaquetado. La historia comienza con archivos ya compuestos, por lo que el diferencial final carece de una medición del esfuerzo invertido. La propagación coordinada en E/F/G, las pruebas de compatibilidad y el mantenimiento de URL, biblioteca y calendario introducen costes que el recuento no cuantifica.

Sin registro de horas, mantenimiento, incidencias, demanda, rendimiento o alternativa comparable, el coste de adaptación y el beneficio económico quedan indeterminados. Si aparece un receptor, el diseño de medición puede fijar un escenario y criterio equivalentes para adaptación e implementación de referencia, y registrar por separado tiempo de integración, pruebas, correcciones y operación. La evidencia actual justifica priorizar una prueba de compatibilidad de bajo coste antes de ampliar arquitectura o automatización.

## 11. Decisiones fundamentadas y pendientes

| Puerta / decisión posible | Fundamento y condición |
| --- | --- |
| G0–G2 · Cerrar caracterización y conservar el mecanismo | Relevancia, viabilidad y diferencial funcional sustentados. Preservar la línea base y reproducibilidad. El diferencial es una capacidad local, sin comparación de rendimiento o valor comercial. |
| G3 · Validar o corregir | El propietario debe decidir si InHouse comparte la regla de despacho, qué puntaje corresponde en cerrado, qué información de cierre se comunica y qué representa `ENVIADO`. Si demanda una semántica diferente, autorizar cambio y fijar primero oráculos para los contraejemplos. Para regresión futura, valorar usar el código real y comprobar valores de congelación. |
| G3 · Ampliar o suspender validación del QR | Si el uso previsto depende de impresión y lectura, verificar biblioteca, destino, lector y manejo de errores con un cliente autorizado. Esta ejecución sustituye la biblioteca y el navegador de la página generadora. |
| G4 · Transferir o archivar por prioridad | Identificar receptor y criterio antes de adaptar. Sin receptor, conservar el activo y el protocolo para evitar pruebas sin decisión. |
| G5 · Inversión o despliegue | Pendiente de evidencia operacional y económica. El informe no ejecuta decisiones de producto ni de infraestructura. |

La contradicción entre pureza literal y reloj implícito, las lecturas de estado persistente y el alcance del filtro de infraestructura se elevan al propietario para resolver su aplicabilidad documental (§2.1). La evidencia contraria delimita afirmaciones específicas. Un descarte del candidato completo requeriría un requisito aplicable y criticidad demostrada.

## 12. Aprendizajes metodológicos y criterios de cierre

La comparación de texto con historial sitúa el cambio sin atribuir a febrero reglas documentadas después. La matriz semanal detecta el caso que el ejemplo artificial de cerrado omitía. La intervención estricta distingue aserciones de comportamiento de aserciones de implementación. El doble de apertura separa el intento local de la operación externa. Estos protocolos son reutilizables si se preservan versiones, condiciones y criterios propios de cada receptor. No se requiere infraestructura experimental adicional para reproducir el resultado local.

**Cierre EQ-R01.** Queda caracterizado el incremento tecnológico, la conservación local, el alcance formal defendible y las condiciones de transferencia. La evidencia incluye controles, resultados contrarios, incertidumbres y desviación del oráculo. La fiabilidad del QR en campo, la semántica deseada de disponibilidad y entrega, la transferencia a un receptor distinto y la ventaja económica permanecen abiertas. Reabrir ante un requisito definido, un receptor identificado o evidencia operativa que pueda cambiar una decisión. La revisión posterior confirma que las pruebas ejercitaron los objetos fijados y que el informe conserva las conclusiones con sus condiciones (§§19–23).

### Apéndice reproducible · P1 v2, P2 v1 y P3 HTML

Extraer el siguiente bloque a un archivo temporal y, desde EscanningQR, ejecutar `TZ=America/Guayaquil node /ruta/eq-r01.cjs /ruta/almuerzos-ecuador`, con ambos objetos Git disponibles. Para P3 CLI, ejecutar `git show b81c173:validacion-cli.js | node` e inspeccionar el recuento. Para P0, comparar cada archivo compartido extraído de los dos commits con `diff -u --strip-trailing-cr` y consultar `git log --reverse --name-status` en cada repositorio.

```js
const assert = require('node:assert/strict');
const vm = require('node:vm');
const {execFileSync} = require('node:child_process');
const eq = 'b81c173f5325a382bb15ba29d246db7b9fdf22ef';
const ae = '5a19920ab0a8a6169e4b725b308506d7d93c75f6';
const read = (repo, rev, file) => execFileSync('git', ['-C', repo, 'show', rev+':'+file], {encoding:'utf8'});
const EQ = f => read(process.cwd(), eq, f);
const AE = f => read(process.argv[2], ae, f);
const plain = x => JSON.parse(JSON.stringify(x));
const js = html => [...html.matchAll(/<script>([\s\S]*?)<\/script>/g)].map(x=>x[1]).join('\n');
let instant = Date.parse('2026-01-19T00:00:00-05:00');
function load(source, search='', denied=false) {
  let allow = false;
  const events = [], ticks = [];
  const window = {location:{search}, open:(...args)=>{events.push(['open',...args]);return null;}};
  const context=vm.createContext({
    window, URLSearchParams, module:{exports:{}}, console:{log(){},error(){}},
    Date:class extends Date {constructor(){super(instant);}},
    localStorage:{getItem(){if(denied)throw Error('denied');return '000';},setItem(){}},
    setInterval:(fn,ms)=>{assert.equal(ms,60000); ticks.push(fn);},
    alert:()=>events.push(['alert']), confirm:()=>{events.push(['confirm']);return allow;},
    mostrarMensajeConfirmacion:()=>events.push(['feedback'])
  });
  for(const f of ['menu.js','sistema.js']) vm.runInContext(source(f),context,{filename:f});
  return {...context.module.exports, context, menu:vm.runInContext('MENU_DATA',context),
    window, events, ticks, accept:()=>{allow=true;}};
}
async function main(){
  const old=load(AE), cur=load(EQ);
  assert.deepEqual(plain(cur.menu),plain(old.menu));
  for(const block of ['Pedido','Tiempo'])
    for(const k of Object.keys(old[block]))
      assert.equal(String(cur[block][k]).replace(/\r/g,''),String(old[block][k]).replace(/\r/g,''));
  const empty=old.Pedido.reset();
  const order=old.Pedido.toggleExtra(old.Pedido.setBase(empty,'B',2),'JUGO');
  const start=instant, changes={};
  for(let i=0;i<7*1440;i++){
    instant=start+i*60000;
    const t=cur.Tiempo.obtenerEstado();
    assert.deepEqual(plain(t),plain(old.Tiempo.obtenerEstado()));
    for(const p of [empty,order]){
      const baseline=old.Reglas.evaluar(p,t);
      const normal=cur.Reglas.evaluar(p,t,{modo:'normal'});
      const inside=cur.Reglas.evaluar(p,t,{modo:'inhouse'});
      assert.deepEqual(plain(normal),plain(baseline));
      assert.deepEqual(plain(cur.Reglas.evaluar(p,t)),plain(baseline));
      assert.deepEqual(plain(inside),{...plain(normal),despachoAsignado:null,
        puntos:normal.ejecutabilidad==='AHORA'?3:normal.puntos});
      const msg=old.Traductor.generarMensaje(p,baseline,t,old.menu);
      assert.equal(cur.Traductor.generarMensaje(p,normal,t,cur.menu),msg);
      assert.equal(cur.Traductor.generarMensaje(p,normal,t,cur.menu,{modo:'normal'}),msg);
      const inmsg=cur.Traductor.generarMensaje(p,inside,t,cur.menu,{modo:'inhouse'});
      if(p===empty) assert.equal(inmsg,null);
      else {
        assert.match(inmsg,/^\*🍽️ PEDIDO DE ALMUERZO\*\n🏠 IN THE HOUSE\n/);
        assert.match(inmsg,/2 × .*Almuerzo B[\s\S]*Jugo/);
        assert.doesNotMatch(inmsg,/Despacho estimado|fuera de horario regular/);
        if(inside.puntos) assert.ok(inmsg.includes("Puntos:* "+inside.puntos));
        else assert.doesNotMatch(inmsg,/Puntos:/);
        const key=normal.motivo || normal.estadoMercado;
        changes[key]=(changes[key]||0)+1;
      }
    }
  }
  console.log('10080 minutos x 2 pedidos', JSON.stringify(changes));
  for(const [q, mode] of [['','normal'],['?modo=inhouse','inhouse'],['?modo=InHouse','normal'],
      ['?modo=otro&modo=inhouse','normal'],['?modo=%69nhouse','inhouse']]){
    instant=start+660*60000;
    const a=load(EQ,q), g=a.Sistema;
    await g.iniciar();
    assert.equal(g.estado,'LISTO');
    assert.equal(g.contexto.modo,mode);
    assert.ok(Object.isFrozen(g.contexto));
    const ctx=g.contexto;
    a.window.location.search='?modo='+ (mode==='normal'?'inhouse':'normal');
    assert.equal(a.events.length,0);
    g.enviarPedido();
    assert.deepEqual(a.events.splice(0),[['alert']]);
    g.callbacks.onAjustarBase('A',1);
    g.callbacks.onAjustarBase('B',1);
    g.callbacks.onAjustarBase('A',1);
    g.callbacks.onExtra('JUGO');
    const order=g.pedido;
    assert.deepEqual(plain(order),{bases:[{id:'B',cantidad:1},{id:'A',cantidad:2}],extras:['JUGO']});
    assert.equal(g.evaluacion.puntos,mode==='inhouse'?3:1);
    assert.equal(g.evaluacion.despachoAsignado,mode==='inhouse'?null:'12:00');
    instant=start+840*60000;
    a.ticks[0]();
    assert.equal(g.pedido,order);
    assert.equal(g.contexto,ctx);
    assert.equal(g.evaluacion.motivo,'SIN_DESPACHO');
    g.callbacks.onEnviar();
    assert.deepEqual(a.events.splice(0),[['confirm']]);
    a.accept();
    g.callbacks.onEnviar();
    assert.deepEqual(a.events.map(e=>e[0]),['confirm','open','feedback']);
    const url=new URL(a.events[1][1]);
    assert.equal(url.origin,'https://wa.me');
    assert.equal(url.pathname,'/000');
    assert.equal(a.events[1][2],'_blank');
    const msg=url.searchParams.get('text');
    assert.equal(msg.includes('IN THE HOUSE'),mode==='inhouse');
    assert.equal(msg.includes('fuera de horario regular'),mode==='normal');
    assert.equal(g.estado,'ENVIADO');
    g.callbacks.onReset();
    g.callbacks.onAjustarBase('A',1);
    assert.equal(g.pedido.bases[0].cantidad,1);
  }
  const denied=load(EQ,'',true);
  await denied.Sistema.iniciar();
  assert.equal(denied.Sistema.estado,'ERROR');
  assert.deepEqual(denied.events,[['alert']]);
  assert.equal(denied.ticks.length,0);
  const probe=load(EQ,'?modo=inhouse');
  instant=start+660*60000;
  await probe.Sistema.iniciar();
  probe.Sistema.contexto={modo:'normal'};
  probe.ticks[0]();
  assert.equal(probe.Sistema.evaluacion.despachoAsignado,'12:00');
  probe.Sistema.ajustarBase('A',1);
  const evaluation=probe.Sistema.evaluacion;
  assert.match(probe.Traductor.generarMensaje(probe.Sistema.pedido,evaluation,
    probe.Sistema.tiempo,probe.menu,{modo:'inhouse'}),/IN THE HOUSE[\s\S]*Despacho estimado/);
  console.log('5 consultas, reloj y gestos, cancelación, apertura nula, error de almacenamiento, reasignación y contexto incoherente: verificados');

  const qr=EQ('generadorqr.html'), element={}, calls=[];
  function QRCode(...args){calls.push(args);}
  QRCode.CorrectLevel={H:'H'};
  vm.runInNewContext(js(qr),{document:{getElementById:id=>{assert.equal(id,'qrcode');return element;}},QRCode});
  assert.equal(calls.length,1);
  assert.equal(calls[0][0],element);
  assert.deepEqual(plain(calls[0][1]),{text:'https://ksgfin8-cyber.github.io/escanningqr/?modo=inhouse',width:300,height:300,correctLevel:'H'});
  assert.throws(()=>vm.runInNewContext(js(qr),{document:{getElementById:()=>element}}),{name:'ReferenceError'});
  console.log('QR: parámetros capturados; falta de biblioteca => ReferenceError');
  const v=load(EQ), out=[];
  v.context.document={getElementById:()=>({appendChild:n=>out.push(n)}),createElement:()=>({})};
  const html=js(EQ('validacion.html'));
  for(const [code,fail] of [[html,2],['"use strict";\n'+html,0]]) {
    const w=load(EQ);
    w.context.document=v.context.document;
    vm.runInContext(code,w.context);
    const stats=plain(vm.runInContext('({passCount,failCount,total,frozen:Object.isFrozen(contextoNormal)&&Object.isFrozen(contextoInhouse),modes:[contextoNormal.modo,contextoInhouse.modo]})',w.context));
    assert.deepEqual(stats,{passCount:34-fail,failCount:fail,total:34,frozen:true,modes:['normal','inhouse']});
    console.log('HTML',JSON.stringify(stats));
  }
}
main().catch(e=>{console.error(e);process.exitCode=1;});
```
