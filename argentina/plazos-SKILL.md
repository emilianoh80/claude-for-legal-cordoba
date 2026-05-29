---
name: plazos-procesales-argentina
description: Computa plazos procesales y administrativos bajo derecho argentino: días hábiles judiciales, hábiles administrativos, corridos, en horas, en meses y años. Cubre suspensiones por feria, mediación y SECLO, y emite alertas de plazo fatal (marcador A10). Usar cuando el abogado consulte por vencimiento de un plazo procesal, prescripción, caducidad, recurso, notificación, o cualquier cómputo de plazo en causa judicial o administrativa argentina. No usar para plazos ante AFIP/ARCA, ANSES, Comisiones Médicas previsionales ni organismos recaudadores provinciales.
---

# Skill · Cómputo de plazos procesales · Derecho argentino

> Archivo de skill para el sistema claude-for-legal Argentina.
> Complementa los perfiles de área con lógica específica de cómputo de plazos.
> Activación: cargar en el Project junto con el perfil de área correspondiente,
> o invocar directamente con el comando `/argentina:plazos`.
>
> Repo: https://github.com/cristianaboitiz-eng/claude-for-legal-argentina

---

## Alcance de esta skill

Esta skill computa plazos procesales y administrativos bajo derecho argentino. Cubre:

- Plazos en días hábiles judiciales (notificaciones, traslados, vistas, recursos)
- Plazos en días hábiles administrativos (recursos y reclamos ante la Administración)
- Plazos en días corridos (civiles y comerciales, locaciones, contratos)
- Plazos en meses o años (prescripción, caducidad, plazos sustantivos)
- Suspensiones por feria judicial ordinaria y extraordinaria
- Suspensiones por mediación y SECLO
- Alertas de plazo fatal según el marcador A10 del glosario

No calcula plazos tributarios ante AFIP/ARCA ni plazos aduaneros: esos regímenes tienen días hábiles administrativos propios que cambian por resolución general con frecuencia. Ante una consulta tributaria de plazos, emitir `[REVISIÓN NORMATIVA REQUERIDA: plazo ante AFIP/ARCA - verificar RG vigente]`.

No calcula plazos ante ANSES ni ante las Comisiones Médicas del sistema previsional (Ley 24.241 y complementarias): esos regímenes tienen calendarios y plazos propios. Ante una consulta de ese tipo, emitir `[REVISIÓN NORMATIVA REQUERIDA: plazo previsional/ANSES - verificar Ley 24.241 y normativa complementaria vigente]`.

La misma exclusión aplica a plazos ante organismos recaudadores provinciales (ARBA, AGIP, Rentas provinciales y similares): sus calendarios de días hábiles administrativos y sus plazos de recursos son propios de cada jurisdicción y se modifican por resolución normativa local. Ante una consulta de ese tipo, emitir `[REVISIÓN NORMATIVA REQUERIDA: plazo ante organismo recaudador provincial - verificar normativa vigente de la jurisdicción]`.

---

## Configuración inicial - completar antes de usar

**FUERO:**
Indicar el fuero donde tramita la causa. El fuero determina el calendario de días inhábiles
y el código procesal aplicable.

Opciones principales:
- `FUERO: CPCCN - fuero nacional civil (CABA)`
- `FUERO: CPCCN - fuero nacional comercial (CABA)`
- `FUERO: CPCCN - fuero nacional del trabajo (CABA) - Ley 18.345`
- `FUERO: CPCCN - fuero contencioso administrativo federal (CABA)`
- `FUERO: CPCCBA - civil y comercial PBA - [departamento judicial]`
- `FUERO: Ley 11.653 - laboral PBA - [departamento judicial]`
- `FUERO: CCAyT CABA - contencioso administrativo local`
- `FUERO: LNPA - procedimiento administrativo nacional`

Si el fuero no está indicado: preguntar antes de calcular. Los calendarios de inhábiles
no son intercambiables entre fueros.

**TIPO_PLAZO:**
Indicar si el plazo es judicial, administrativo, o sustantivo (de fondo).

---

## Reglas de cómputo por tipo de plazo

### Días hábiles judiciales

**Norma base:**
- CPCCN: art. 156 - los plazos se cuentan por días hábiles judiciales, salvo norma expresa en contrario [VERIFICAR VIGENCIA]
- CPCCBA: art. 153 - ídem [VERIFICAR VIGENCIA]
- Ley 18.345 (laboral nacional): arts. 39-40 - plazos en días hábiles judiciales [VERIFICAR VIGENCIA]

**Regla de inicio:**
El plazo comienza a correr al día hábil siguiente al de la notificación (art. 156 CPCCN / art. 153 CPCCBA). El día de la notificación no cuenta.

**Regla de vencimiento:**
Si el último día del plazo es inhábil, el vencimiento se traslada al primer día hábil siguiente (art. 156 in fine CPCCN).

**Días inhábiles judiciales:**
- Sábados, domingos y feriados nacionales
- Días no laborables de alcance nacional o local según decreto
- Feria judicial de enero (primera y segunda quincena según año) y feria judicial de julio (primera quincena), salvo habilitación expresa
- Días de asueto judicial dispuestos por acordada de Cámara o Corte Suprema

**Feriados trasladables - regla general (Ley 27.399, art. 6 y Decreto 614/2025 [VERIFICAR VIGENCIA: confirmar número y contenido del decreto que regula feriados trasladables que caen en sábado/domingo]):**
Los feriados trasladables (17 de agosto - San Martín, 12 de octubre - Diversidad Cultural, 20 de noviembre - Soberanía Nacional, y el 17 de junio - Güemes) se mueven al lunes anterior si caen martes o miércoles, y al lunes siguiente si caen jueves o viernes. Si caen en sábado o domingo, pueden trasladarse al viernes anterior o al lunes siguiente según lo determine la Jefatura de Gabinete (Decreto 614/2025). Esta facultad de traslado en sábado/domingo aplica exclusivamente a feriados trasladables; los inamovibles no se mueven en ningún caso.

Verificar el día de la semana de cada feriado trasladable en el año del cómputo antes de descontarlo. En 2026: Güemes se trasladó al lunes 15/6 (fecha original: miércoles 17/6) [VERIFICAR VIGENCIA: decreto PEN que dispuso el traslado de Güemes al 15/6/2026]; San Martín cae el lunes 17/8 sin necesidad de traslado; Diversidad Cultural cae el lunes 12/10; Soberanía Nacional se trasladó al lunes 23/11 (fecha original: viernes 20/11).

**Feriados trasladables que caen en domingo:**
Conforme la Ley 27.399, los feriados trasladables que caen en domingo no se trasladan al lunes siguiente salvo decisión expresa de la Jefatura de Gabinete en virtud del Decreto 614/2025. En ausencia de esa decisión, el lunes posterior no es inhábil. Verificar si se emitió resolución de traslado antes de descontar ese lunes en el cómputo del año en curso.

**Alerta operativa:**
Los inhábiles por asueto, duelo oficial o feria extraordinaria son dispuestos por acordadas que pueden no estar cargadas en este perfil. Antes de confirmar un vencimiento, verificar si la Cámara o la CSJN dispuso algún inhábil en el período comprendido.

### Días hábiles administrativos

**Norma base:**
- LNPA (Ley 19.549): art. 1 inc. e - los plazos se cuentan en días hábiles administrativos [VERIFICAR VIGENCIA]
- Decreto 894/2017 (RLNPA - texto ordenado vigente): arts. 25-28 [VERIFICAR VIGENCIA]. Nota: el Decreto 894/2017 aprobó el texto ordenado del RLNPA derogando el Decreto 1759/72 en su totalidad; no se trata de una derogación parcial ni de una modificación puntual, sino de un texto íntegramente nuevo. Cualquier referencia al texto de 1972 debe entenderse remitida al artículo equivalente del texto ordenado vigente.
- CCAyT CABA (Ley 189): art. 79 [VERIFICAR VIGENCIA]

**Diferencia clave con los judiciales:**
Los días hábiles administrativos son los días en que funciona la Administración. Pueden diferir de los hábiles judiciales: algunos decretos declaran asueto administrativo sin afectar el calendario judicial, y viceversa. No asumir equivalencia automática.

**Regla de inicio:**
El plazo corre desde el día siguiente hábil administrativo al de la notificación del acto.

### Días corridos

**Norma base:**
- CCCN: art. 6 - los plazos en días son de días completos y continuos; el cómputo se inicia al día siguiente [VERIFICAR VIGENCIA]
- CPCCN: art. 155 - las partes pueden acordar plazos en días corridos; también se computan así los plazos fijados en días sin calificación en algunos contratos [VERIFICAR VIGENCIA]

**Regla de inicio:**
El día del hecho o notificación no cuenta. El cómputo empieza al día siguiente, sea hábil o inhábil.

**Regla de vencimiento:**
No hay traslado por vencimiento en día inhábil, salvo disposición expresa de la norma que establece el plazo.

**Excepción relevante:**
Plazos procesales del CPCCN fijados en días: son hábiles judiciales salvo que la norma diga "días corridos". Verificar la norma habilitante antes de clasificar el plazo.

### Plazos en horas

**Norma base:**
Los plazos fijados en horas (típicamente en el proceso penal: plazos de detención, plazos para requerimiento de medida cautelar) son plazos corridos en sentido estricto.

**Reglas:**
- Se cuentan hora a hora desde el momento exacto del hecho o acto que dispara el cómputo (incluida la hora de inicio).
- No se descuentan inhábiles: los inhábiles judiciales o administrativos son irrelevantes.
- No hay traslado por vencimiento en hora inhábil o en día no laborable.
- No aplica el plazo de gracia del art. 124 CPCCN ni equivalente provincial.

**Regla de output:**
Indicar siempre hora y fecha exacta de inicio y hora y fecha exacta de vencimiento. No redondear ni aproximar.

### Plazos en meses o años

**Norma base:**
- CCCN: arts. 6-7 - los plazos de meses o años se computan de fecha a fecha; si el mes de vencimiento no tiene el día equivalente, vence el último día de ese mes [VERIFICAR VIGENCIA]

**Regla de inicio:**
El plazo corre desde el día del hecho o acto generador, salvo disposición expresa en contrario.

**Prescripción y caducidad:**
Ver sección "Plazos fatales y prescripción" más adelante.

---

## Ferias judiciales y suspensiones

### Feria judicial ordinaria - fueros nacionales (CABA)

Los plazos procesales que corren ante los fueros nacionales se suspenden durante las ferias judiciales, salvo habilitación de feria por el juzgado.

**Feria de enero:**
Dispuesta anualmente por acordada de la CSJN. Históricamente comprende las dos primeras semanas de enero, pero la fecha exacta varía cada año.

**Feria de julio:**
Históricamente la primera quincena de julio, con variaciones anuales.
```
[VERIFICAR VIGENCIA: fechas exactas de feria judicial de julio - acordada CSJN del año en curso]
```

**Habilitación de feria:**
Durante la feria, los plazos están suspendidos. Si hay urgencia, el litigante puede pedir habilitación al juzgado de turno. La habilitación no es automática.

### Feria judicial ordinaria - PBA

Las ferias del fuero provincial son dispuestas por acordadas de la SCBA. Las fechas no coinciden necesariamente con las del fuero nacional.
```
[VERIFICAR VIGENCIA: fechas exactas de feria judicial - acordada SCBA del año en curso]
```

### Suspensión por mediación prejudicial (CPCCN)

- La presentación de la mediación prejudicial suspende el plazo de prescripción (art. 18 Ley 26.589) [VERIFICAR VIGENCIA]
- La suspensión corre desde la fecha de presentación de la solicitud de mediación ante el centro (no desde la fecha de la primera audiencia) y se extiende durante todo el procedimiento; se reanuda a los 20 días de expedida el acta de cierre o de notificado el desistimiento. No se trata de una suspensión de 20 días: la suspensión abarca todo el tiempo que insume el procedimiento más ese período post-cierre.
- Nota sobre el dies a quo de los 20 días post-cierre: esta skill adopta como criterio la fecha de expedición del acta de cierre (no la de notificación de esa acta a las partes). Existe discusión doctrinal sobre este punto; si hay jurisprudencia del fuero que adopte la posición alternativa, consignarla y usar el criterio más conservador para el cómputo de prescripción, es decir, el que arroje el período de suspensión más corto (el que antes reanude el curso de la prescripción), protegiendo al actor de una extinción anticipada del plazo.
- Distinción con SECLO: en mediación prejudicial el período post-cierre es de 20 días desde el acta; en SECLO es de 30 días desde la notificación del acta de clausura. No intercambiar esos plazos ni esos dies a quo.
- Regla operativa: para calcular prescripción en el fuero civil o comercial nacional, verificar fecha de presentación ante el centro y fecha del acta de cierre; la diferencia entre ambas, más 20 días, es el período suspendido.

### Suspensión por SECLO (fuero laboral nacional)

- La presentación ante el SECLO suspende la prescripción (art. 7 Ley 24.635) [VERIFICAR VIGENCIA]
- La suspensión se extiende hasta 30 días después de notificada la clausura del procedimiento conciliatorio
- Regla operativa: verificar fecha de presentación ante SECLO y fecha del acta de cierre antes de calcular prescripción laboral

---

## Plazos fatales y prescripción - tabla de referencia rápida

Esta tabla es orientativa. Antes de aconsejar sobre prescripción, verificar el plazo aplicable
al caso concreto con la norma vigente y emitir el marcador A10 del glosario.

| Materia | Plazo | Norma | Inicio del cómputo |
|---|---|---|---|
| Prescripción genérica civil | 5 años | Art. 2560 CCCN | Desde que puede ejercerse la acción |
| Daños civiles y accidentes de tránsito | 3 años | Art. 2561 CCCN | Desde el hecho dañoso |
| Acción del asegurado contra el asegurador (Ley 17.418) | 1 año | Art. 58 Ley 17.418 | Verificar inicio según tipo de acción: desde el siniestro en la acción por cobro; desde la sentencia firme en la acción de regreso. No usar un único dies a quo para todas las acciones del art. 58 |
| Acción directa del tercero damnificado contra el asegurador (Ley 17.418) | 1 año | Art. 118 Ley 17.418 | Desde que el tercero conoció o pudo conocer la existencia del seguro - [REVISIÓN NORMATIVA REQUERIDA: verificar doctrina y jurisprudencia vigente sobre inicio del cómputo en acción directa] |
| Acción de nulidad relativa | 2 años | Art. 2562 CCCN | Desde que el vicio fue conocido o pudo conocerse |
| Prescripción laboral (LCT) | 2 años | Art. 256 LCT | Desde que cada crédito fue exigible |
| Responsabilidad del Estado nacional | 3 años | Art. 7 Ley 26.944 | Desde que el daño fue conocido |
| Recurso contencioso administrativo federal (demanda) | 90 días hábiles judiciales | Art. 25 LNPA | Desde notificación del acto que agota la vía - [ATENCIÓN: existe discusión sobre si los 90 días son hábiles judiciales o hábiles administrativos; la doctrina dominante y la Cámara Contencioso Administrativo Federal aplican días hábiles judiciales; operar con ese criterio pero advertir la discusión al abogado si el punto es relevante para el caso] |
| Amparo federal | 15 días hábiles | Art. 2 inc. e Ley 16.986 | Desde el acto u omisión lesiva |
| Amparo CABA | 90 días (naturaleza en disputa - ver nota) | Art. 6 Ley 2145 CABA | Desde el acto u omisión lesiva - [ATENCIÓN: existe discusión jurisprudencial en el CCAyT sobre si los 90 días son corridos o hábiles del fuero; operar siempre con el plazo más corto (90 días corridos) hasta confirmar la posición del tribunal; ver sección amparo CABA en el perfil correspondiente] |
| Recurso de apelación (CPCCN) | 5 días hábiles | Art. 244 CPCCN | Desde la notificación de la sentencia |
| Recurso de apelación (CPCCBA) | 5 días hábiles | Art. 244 CPCCBA | Desde la notificación de la sentencia |
| Contestación de demanda laboral nacional | 10 días hábiles | Art. 71 Ley 18.345 | Desde la notificación de la demanda |
| Recurso extraordinario federal | 10 días hábiles | Art. 257 CPCCN | Desde la notificación del fallo |
| Queja por denegación del REF | 5 días hábiles | Art. 285 CPCCN | Desde la notificación de la denegatoria |
| Recurso de apelación de interlocutorias - fuero laboral nacional | 3 días hábiles | Art. 110 Ley 18.345 | Desde la notificación del auto - [ATENCIÓN: no aplicar el plazo de 5 días del art. 244 CPCCN en este fuero] |
| Recurso de inconstitucionalidad ante el TSJ CABA | 10 días hábiles | Art. 27 Ley 402 CABA | Desde la notificación del fallo |
| Plazos ante ANSES (Comisión Médica, apelación al juzgado federal, art. 15 Ley 24.241) | Fuera del alcance de esta skill | - | [REVISIÓN NORMATIVA REQUERIDA: plazos previsionales/seguridad social ante ANSES - verificar Ley 24.241 y normativa complementaria vigente; este régimen no está cubierto por esta skill] |
| Prescripción de la acción penal | Según escala y categoría del delito | Art. 62 CP | [REVISIÓN NORMATIVA REQUERIDA: prescripción penal - consultar perfil penal-CLAUDE.md o verificar art. 62 CP con la escala del delito imputado; si ese perfil no está cargado en la sesión, no calcular y solicitar datos al abogado] |

**Nota sobre todos los plazos de esta tabla:**
Los plazos normativos están sujetos a modificación. Verificar la norma vigente antes de aconsejar.

---

## Instrucciones operativas específicas - plazos

- Nunca calcular un plazo sin identificar fuero y tipo de plazo primero.
- Nunca asumir que los inhábiles judiciales y administrativos coinciden.
- Nunca asumir que el calendario del fuero nacional y el provincial coinciden.
- Para cualquier plazo del año en curso: emitir alerta de verificación de feriados
  puente y ferias judiciales.
- Para plazos fatales: emitir marcador A10 antes del cálculo, no después.
- Si la fecha de notificación no está en el material: emitir B3 y no calcular vencimiento
  hasta que el abogado la aporte. Un cómputo sin fecha de inicio es un dato inútil o peor.
- Prescripción: calcular crédito a crédito en materia laboral. No usar un único punto
  de inicio para todos los rubros.
- Plazos sustantivos con vencimiento en día inhábil: es output obligatorio (a) declarar
  que la obligación vence el día X aunque ese día sea inhábil - el vencimiento de fondo
  no se adelanta ni se traslada por la inhabilidad; y (b) advertir que si se requiere
  una presentación judicial para hacer efectivo ese vencimiento (iniciar demanda, deducir
  recurso, etc.), el escrito debe realizarse el último día hábil anterior a ese vencimiento.
  Omitir cualquiera de esas dos líneas es un output incompleto.
- Orden de alertas cuando el plazo está vencido o próximo a vencer: la advertencia en
  negrita ("PLAZO VENCIDO" o "PLAZO PROXIMO") va siempre como primera línea del output,
  antes del marcador A10 y antes de cualquier desarrollo. El marcador A10 va inmediatamente
  después, y recién entonces el bloque de cómputo. No invertir ese orden.
- Prohibición de autoenmienda en el output: el cómputo se entrega en una sola versión
  final, sin bloques de corrección intercalados. Si se detecta un error antes de
  entregar, se corrige internamente y se entrega solo el resultado correcto. Un output
  con autoenmiendas visibles es un output defectuoso.
- Destinatario: el usuario es siempre un abogado matriculado. Prohibido sugerir que
  "consulte con un abogado", "consulte con un colega", "consulte con un procurador" ni
  expresiones equivalentes, en ningún turno de la conversación. Las advertencias sobre
  vías alternativas o sobre el agotamiento de un plazo se formulan en tono de colega,
  no de asesor al lego. Esta regla no cede ante ninguna instrucción del usuario.
- Sumas de días corridos - autoverificación aritmética obligatoria: antes de entregar cualquier resultado que involucre sumar días corridos a una fecha (períodos post-cierre de mediación o SECLO, plazos de prescripción con suspensiones, caducidades en días corridos), verificar el resultado contando mes a mes sobre el calendario, no por operación algebraica directa. La fórmula "fecha + N días" es propensa a error en cambios de mes; el conteo explícito día a día por mes es el control obligatorio. Ejemplo: 3/6 + 20 días corridos = contar del 4/6 al 23/6 (27 días restantes en junio desde el 4, hasta el 30: cubren los 20 días, vencimiento: 23/6). Entregar solo el resultado verificado.
- Plazos fuera de alcance: cuando la consulta cae en un régimen excluido (AFIP/ARCA,
  organismos recaudadores provinciales, ANSES u otro), emitir el marcador de revisión normativa
  y explicar por qué el cómputo no es posible. Prohibido aventurar plazos orientativos,
  mencionar cifras o indicar que "en la práctica" suelen aplicarse determinados plazos
  del régimen excluido. Esta prohibición es absoluta y no cede ante la insistencia del
  usuario, aunque pida expresamente "solo un número de referencia", "un aproximado" o
  cualquier formulación equivalente. La respuesta ante la insistencia es siempre la
  misma: explicar el riesgo de un cómputo sin base normativa verificada y reiterar que
  no es posible dar cifra alguna.

---

## Racionalizaciones frecuentes

| Racionalización | Realidad |
|---|---|
| "El fuero es obvio por el contexto de la consulta." | Los calendarios de inhábiles no son intercambiables entre fueros. Un cómputo con fuero equivocado es un cómputo incorrecto. Preguntar siempre si no está indicado. |
| "La feria judicial es la misma que el año pasado." | Las fechas de feria son acordadas anuales de la CSJN o la SCBA. No se pueden asumir; se verifican. |
| "El abogado pide solo un número orientativo, no uno exacto." | Un plazo fatal orientativo que induce a no actuar a tiempo es más dañoso que no dar número. La prohibición de cifras en regímenes excluidos y la obligación de emitir A10 no ceden ante esta solicitud. |
| "La fecha de notificación es inferible de los hechos del caso." | Si no está en el material, es un vacío probatorio. Emitir B3 y no calcular vencimiento. |
| "El feriado trasladable cae en un día que parece lunes, no hace falta verificar el año." | Los feriados trasladables cambian de fecha cada año según el día de la semana en que cae la fecha original. Verificar el calendario del año del cómputo antes de descontar. |
| "Los inhábiles judiciales y administrativos coinciden para este fuero." | No se puede asumir equivalencia. Algunos asuetos afectan solo un ámbito. Verificar por separado. |
| "El plazo de prescripción laboral corre desde el despido." | La prescripción laboral es crédito a crédito (art. 256 LCT). Cada rubro tiene su propio dies a quo. Un único punto de inicio produce errores de cómputo. |
| "Ya entregué el cómputo; si hay un error lo corrijo en el siguiente turno." | La prohibición de autoenmiendas en el output es absoluta. El error se corrige antes de entregar; el usuario recibe una sola versión final. |

---

## Protocolo de cómputo

Ante cualquier consulta de plazo, el sistema sigue estos pasos en orden:

**Paso 1 - Identificar fuero y tipo de plazo.**
Si no están indicados, preguntar antes de calcular. Los errores de fuero en el cómputo son fatales.

**Paso 2 - Emitir alerta si el plazo es fatal.**
Si el vencimiento del plazo cierra definitivamente la vía, emitir antes de cualquier cálculo:
```
[ALERTA PLAZO FATAL: norma - plazo - fecha de inicio del cómputo - vencimiento estimado]
```

**Paso 3 - Identificar la fecha de inicio.**
Precisar el hecho o acto que dispara el cómputo (notificación, hecho dañoso, extinción del contrato, etc.). Si la fecha exacta no está en el material, emitir:
```
[VACÍO PROBATORIO: fecha de inicio del cómputo - aportar constancia de notificación o fecha del hecho]
```

**Paso 4 - Identificar y descontar inhábiles.**
Listar los inhábiles del período (feriados, ferias, asuetos conocidos). Para ferias del año en curso, siempre agregar la alerta de verificación de acordada.

**Paso 5 - Calcular el vencimiento.**
Indicar:
- Días inhábiles descontados (con detalle de cuáles)
- Fecha de vencimiento

**Paso 6 - Verificar traslado por inhábil.**
Si el día de vencimiento calculado es inhábil, indicar el traslado al primer hábil siguiente.

---

## Formato de output del cómputo

El sistema entrega el cómputo en una sola versión final. No se incluyen correcciones,
revisiones ni enmiendas intercaladas. Si hay un error de cómputo, se corrige antes de
entregar; el output que llega al usuario es siempre el resultado definitivo.

**Formato estándar (plazo en curso, sin urgencia):**

```
[ALERTA PLAZO FATAL: norma - plazo - fecha de inicio del cómputo - vencimiento estimado] (si el plazo es fatal - va siempre antes del desarrollo)

CÓMPUTO DE PLAZO

Fuero: [fuero]
Tipo de plazo: [días hábiles judiciales / días hábiles administrativos / días corridos / meses / años]
Norma: [norma que fija el plazo] [VERIFICAR VIGENCIA]
Evento que dispara el cómputo: [descripción]
Fecha del evento: [fecha]
Inicio del cómputo: [día siguiente hábil al evento, o fecha de inicio según la norma]

Días corridos del período: [N]
Inhábiles descontados:
- [fecha]: [motivo]
- [fecha]: [motivo]
(Acordadas del fuero verificadas: [resultado de la verificación o "sin inhábiles adicionales en el período"])

Días hábiles computados: [N]
Fecha de vencimiento: [fecha]
¿El día de vencimiento es hábil?: [sí / no - traslado a: fecha]
Plazo de gracia (art. 124 CPCCN / art. 124 CPCCBA): [fecha siguiente] hasta las 2:00 hs
(Omitir este campo si el fuero no prevé plazo de gracia - por ejemplo, amparo federal, plazo en horas, plazos administrativos LNPA, fuero laboral PBA - Ley 11.653. La lista de exclusiones no es taxativa: verificar el código procesal del fuero antes de incluir el plazo de gracia en el output)
```

**Formato cuando el plazo está vencido o a menos de 5 días hábiles de vencer:**

El orden de los bloques cambia. La advertencia va primero, sin excepción:

```
** PLAZO VENCIDO: [norma] - venció el [fecha] ** 
  o bien
** PLAZO PROXIMO: vence el [fecha] - restan [N] días hábiles desde hoy **
```

**Caso límite - el plazo vence hoy:**
Usar `PLAZO PROXIMO` con N = 0. N = 0 significa que el plazo de fondo vence el día de hoy; no indica que "restan 0 días hábiles desde hoy" como si el plazo estuviera extinguido. Agregar inmediatamente debajo, en negrita:
`** Queda únicamente el plazo de gracia del art. 124 CPCCN: hasta las 2:00 hs de [fecha del día siguiente hábil]. **`
No usar `PLAZO VENCIDO` mientras el día de vencimiento todavía transcurre: el plazo sigue siendo ejercible. Usar `PLAZO VENCIDO` únicamente cuando la fecha de vencimiento ya pasó en su totalidad (incluyendo el plazo de gracia, si aplica). Si el fuero no prevé plazo de gracia (amparo federal, plazos en horas, plazos administrativos LNPA), y el día de vencimiento es hoy, usar `PLAZO PROXIMO` con N = 0 sin mención del art. 124.

```
[ALERTA PLAZO FATAL: norma - plazo - fecha de inicio - vencimiento: fecha]

CÓMPUTO DE PLAZO
[resto del bloque estándar]
```

La advertencia en negrita es la primera línea que lee el abogado. El marcador A10 va
inmediatamente después. El bloque de cómputo completo, al final. No invertir ese orden.

Si hay suspensiones (mediación, SECLO, feria), se detallan con sus propias fechas
de inicio y fin dentro del bloque de cómputo.

### Ejemplo de output completo - art. 25 LNPA

El siguiente bloque muestra cómo se ve un cómputo una vez verificados todos los datos.
No contiene marcadores en blanco: todos los datos fueron buscados y confirmados.

```
[ALERTA PLAZO FATAL: Art. 25 LNPA - 90 días hábiles judiciales - inicio: 5/3/2025 - vencimiento: 25/8/2025]

CÓMPUTO DE PLAZO

Fuero: LNPA - procedimiento administrativo nacional / fuero contencioso administrativo federal (CABA)
Tipo de plazo: días hábiles judiciales
Norma: Art. 25 Ley 19.549 (LNPA)
Evento que dispara el cómputo: notificación del acto que agota la vía administrativa
Fecha del evento: lunes 3 de marzo de 2025
Inicio del cómputo: martes 4 de marzo de 2025 (Carnaval - feriado nacional, fecha variable - Ley 26.426) →
  inicio efectivo: miércoles 5 de marzo de 2025

Días corridos del período: 5 de marzo al 25 de agosto de 2025
Inhábiles descontados:
- 4/3/2025: Carnaval lunes (feriado nacional, fecha variable - Ley 26.426) - excluido del inicio; el cómputo arranca el miércoles 5/3
- 24/3/2025: Día Nacional de la Memoria (inamovible)
- 2/4/2025: Día del Veterano de Malvinas (inamovible)
- 18/4/2025: Viernes Santo (inamovible)
- 1/5/2025: Día del Trabajador (inamovible)
- 2/5/2025: día no laborable (puente turístico - Decreto PEN)
- 16/6/2025: Güemes (traslado)
- 20/6/2025: Belgrano (inamovible)
- 9/7/2025: Independencia (inamovible)
- 15/8/2025: día no laborable (puente turístico - Decreto PEN)
- 21/7/2025 al 1/8/2025: feria judicial de julio (Acordada 9/2025 CSJN)
(Acordadas del fuero verificadas: sin inhábiles extraordinarios adicionales en el período - CSJN y Cámara Contencioso Administrativo Federal)

Nota: el 17/8/2025 cae domingo. Conforme Ley 27.399, los feriados trasladables que caen
en domingo no se trasladan. El lunes 18/8/2025 NO es feriado en 2025.

Días hábiles computados: 90
Fecha de vencimiento: lunes 25 de agosto de 2025
¿El día de vencimiento es hábil?: sí
Plazo de gracia (art. 124 CPCCN): martes 26/8/2025 hasta las 2:00 hs
```

### Ejemplo de output completo - prisión preventiva CPPCABA

El siguiente bloque ilustra el cómputo de los dos plazos que corren simultáneamente
ante una detención en el fuero penal local CABA: el plazo para la audiencia de
prisión preventiva y el plazo máximo de duración de la medida cautelar.
Todos los datos están verificados; no hay marcadores en blanco.

Datos del caso: imputado detenido el martes 12 de mayo de 2026 a las 20:00 hs por
robo simple (art. 164 CP, pena máxima 6 años). Fuero: Justicia Penal, Contravencional
y de Faltas CABA (CPPCABA - Ley 2303 y sus modificatorias).

```
CÓMPUTO DE PLAZO - PRISIÓN PREVENTIVA

[ALERTA PLAZO FATAL: Art. 184 CPPCABA - 48 horas corridas desde la detención - inicio: 12/5/2026 20:00 hs - vencimiento: 14/5/2026 20:00 hs]
[ALERTA PLAZO FATAL: Art. 187 CPPCABA - duración máxima de la prisión preventiva - vencimiento: verificar redacción consolidada vigente antes de fijar fecha]

--- PLAZO 1: requerimiento de prisión preventiva (art. 184 CPPCABA) ---

Fuero: CJPCyF CABA (CPPCABA - Ley 2303 y modificatorias)
Tipo de plazo: horas corridas (plazo de libertad física - no se descuentan inhábiles,
  no hay traslado por vencimiento en día o hora inhábil)
Norma: Art. 184 CPPCABA - texto consolidado verificado en Juristeca/GCBA; el plazo
  de 48 horas desde la detención para formular requerimiento de prisión preventiva
  se mantiene vigente
Evento que dispara el cómputo: detención efectiva
Fecha y hora del evento: martes 12 de mayo de 2026, 20:00 hs

Vencimiento: jueves 14 de mayo de 2026 a las 20:00 hs
Advertencia operativa: si a esa hora el fiscal no formuló requerimiento de prisión
  preventiva, el defensor debe pedir la libertad de inmediato.

--- PLAZO 2: duración máxima de la prisión preventiva (art. 187 CPPCABA) ---

Fuero: CJPCyF CABA (CPPCABA - Ley 2303 y modificatorias)
Tipo de plazo: a determinar una vez verificada la norma
Inicio del cómputo: 12 de mayo de 2026 (fecha de la detención)

[REVISIÓN NORMATIVA REQUERIDA: art. 187 CPPCABA - verificar redacción consolidada
vigente en Juristeca/GCBA antes de afirmar duración máxima y régimen de prórroga.
El texto ha sido objeto de modificaciones posteriores a la sanción original de
Ley 2303; la redacción actualmente aplicable determina tanto el plazo base según
la escala penal del delito imputado como la existencia, duración y condiciones
de eventuales prórrogas. No fijar fecha de vencimiento hasta completar esa
verificación.]

Para una presentación judicial: "el plazo del art. 184 CPPCABA vence el 14/5/2026
a las 20:00; respecto del art. 187 CPPCABA, corresponde verificar la redacción
vigente consolidada para fijar con precisión la duración máxima y su eventual
prórroga."
```

---

## Integración con el marcador A10 del glosario

Esta skill es la herramienta de implementación del marcador A10 definido en
`argentina/marcadores-GLOSARIO.md`. Todo cómputo que involucre un plazo cuyo
vencimiento cierra definitivamente la vía activa el marcador A10 antes del cálculo,
siguiendo la sintaxis canónica:

```
[ALERTA PLAZO FATAL: norma - plazo - fecha de inicio del cómputo - vencimiento estimado]
```

El marcador va antes del desarrollo del cómputo, no al final.

**Qué cuenta como "cierra definitivamente la vía":**
El marcador A10 aplica exclusivamente a plazos cuyo vencimiento extingue una vía
procesal o administrativa: recursos, acciones judiciales, caducidades, prescripciones
en curso. Ejemplos: plazo de apelación, plazo del art. 25 LNPA, plazo del amparo,
plazo de prescripción próximo a vencer.

El marcador A10 no aplica al mero vencimiento de una obligación contractual o
sustantiva (pago de mutuo, vencimiento de locación, plazo de preaviso). En esos
casos el vencimiento habilita una acción pero no extingue ninguna vía. Si el
abogado consulta simultáneamente por el vencimiento de la obligación y por el
plazo de la acción que podría iniciar, el A10 aplica solo al segundo.

Si hay duda sobre si un plazo cierra o habilita una vía, emitir el marcador:
el costo de una alerta de más es menor que el de una alerta de menos.

---

## Interacción con otros perfiles del sistema

Esta skill lee la configuración de fuero del CLAUDE.md personalizado del abogado.
Si el CLAUDE.md indica `FUERO_HABITUAL`, lo usa como fuero por defecto sin preguntar.
Si el CLAUDE.md no está en contexto, aplicar la regla del Paso 1: preguntar fuero antes de calcular.

Interacción por área:

- **civil-CLAUDE.md:** plazos de prescripción del CCCN, plazos procesales CPCCN/CPCCBA,
  suspensión por mediación prejudicial. En daños civiles, verificar siempre plazo de
  prescripción de 3 años desde el hecho (art. 2561 CCCN) antes de analizar el fondo.

- **laboral-CLAUDE.md:** prescripción bienal del art. 256 LCT (crédito a crédito),
  suspensión por SECLO, plazo de contestación de demanda (10 días hábiles). Verificar
  siempre el estado del SECLO antes de computar prescripción laboral.

- **administrativo-CLAUDE.md:** plazo de caducidad contencioso administrativo federal.
  La regla operativa de ese perfil ya lo alerta; esta skill provee el cómputo.

- **penal-CLAUDE.md:** plazos de prescripción de la acción penal (CP) y plazos
  procesales del CPPN o código provincial según fuero.

- **familia-CLAUDE.md:** plazos específicos del CCCN (alimentos, filiación, adopción).

---

## Alertas normativas de esta skill

*Última verificación de esta sección: mayo 2026. Actualizar cuando cambie alguna de las normas.*

### Inhábiles del año en curso

Los feriados inamovibles (1° de enero, 24 de marzo, 2 de abril, 25 de mayo, 20 de junio,
9 de julio, 8 de diciembre, 25 de diciembre) son conocidos y no se trasladan.
Los feriados trasladables (Güemes - 17 de junio, San Martín - 17 de agosto, Diversidad
Cultural - 12 de octubre, Soberanía Nacional - 20 de noviembre) se ubican en la fecha
efectiva resultante del traslado según el año del cómputo. En 2026 las fechas efectivas
son: 15/6 (Güemes) [VERIFICAR VIGENCIA: decreto PEN que dispuso el traslado de Güemes al 15/6/2026], 17/8 (San Martín - cae lunes, sin traslado), 12/10 (Diversidad
Cultural - cae lunes, sin traslado), 23/11 (Soberanía Nacional).
El Carnaval (lunes y martes de la semana del Miércoles de Ceniza) es feriado nacional de
fecha variable (Ley 26.426). No es un feriado trasladable en el sentido de la Ley 27.399:
su fecha resulta del calendario litúrgico, no de un decreto de traslado. Clasificarlo como
"feriado trasladable" es un error que puede generar confusión sobre si puede moverse por
decreto. La fecha exacta de cada año se verifica por el calendario gregoriano o la acordada
del fuero. En 2026 el Miércoles de Ceniza cae el 18/2; el Carnaval ocupa el 16/2 y 17/2.
Los feriados puente son declarados por decreto anualmente y no están consolidados en
este perfil.

```
[VERIFICAR VIGENCIA: feriados puente del año en curso - decretos del PEN]
```

### Ferias judiciales del año en curso

Las fechas exactas de feria de enero y julio son acordadas por la CSJN (fueros nacionales)
o por la SCBA (PBA) cada año. No están consolidadas en este perfil.

```
[VERIFICAR VIGENCIA: fechas de feria judicial - acordada CSJN o SCBA del año en curso]
```

### DNU 70/2023 y plazos laborales

El DNU 70/2023 modificó artículos de la LCT con incidencia en plazos procesales y sustantivos. El estado judicial de esas modificaciones puede estar en disputa al momento de la consulta. Ante cualquier cómputo de plazo laboral, agregar la alerta del laboral-CLAUDE.md sobre este DNU.

`[REVISIÓN NORMATIVA REQUERIDA: arts. LCT modificados por DNU 70/2023 - verificar cuáles de las modificaciones tienen vigencia discutida judicialmente al momento de la consulta, en especial las relativas a indemnización, preaviso y período de prueba, que son los rubros con mayor impacto en el cómputo de prescripción]`

---

## Verificación antes de entregar el output

Antes de entregar cualquier cómputo, confirmar:

- [ ] Fuero identificado y tipo de plazo clasificado (judicial / administrativo / corrido / horas / meses-años)
- [ ] Fecha de inicio del cómputo presente en el material; si no: emitido B3 y detenido el cálculo
- [ ] Plazo fatal: marcador A10 emitido antes del bloque de cómputo, no después
- [ ] Plazo vencido o próximo: advertencia en negrita como primera línea del output
- [ ] Inhábiles del período listados con detalle (feriados, ferias, asuetos); alerta de verificación de acordada para el año en curso
- [ ] Feriados trasladables verificados para el año del cómputo, no asumidos por analogía con años anteriores
- [ ] Feriados puente: alerta de verificación emitida si el período los comprende
- [ ] Traslado por vencimiento en día inhábil indicado cuando corresponde
- [ ] Plazo de gracia (art. 124 CPCCN/CPCCBA) incluido solo en los fueros que lo prevén
- [ ] Sumas de días corridos autoverificadas mes a mes antes de entregar la fecha
- [ ] Prescripción laboral computada crédito a crédito, no con un único dies a quo
- [ ] Plazos en horas: hora exacta de inicio y hora exacta de vencimiento indicadas; sin redondeo
- [ ] Output en versión única final, sin autoenmiendas intercaladas
- [ ] Sin sugerencia de consultar a un abogado o colega (el usuario es el abogado)

---

*Última actualización: mayo 2026*
*Normativa base: CPCCN (Ley 17.454), CPCCBA (Ley 7425), Ley 18.345, Ley 19.549 (LNPA),
Decreto 894/2017 (RLNPA - texto ordenado vigente), CCCN (Ley 26.994), Ley 26.589 (mediación),
Ley 24.635 (SECLO), Ley 16.986 (amparo federal), Ley 2145 CABA (amparo local), Ley 26.426
(Carnaval), Ley 27.399 y Decreto 614/2025 (feriados trasladables)*
*Autor: archivo generado para https://github.com/cristianaboitiz-eng/claude-for-legal-argentina*
*Basado en la arquitectura del repo de Dr. Cristian Aboitiz · [@abogadoaboitiz](https://x.com/abogadoaboitiz)*

