# Casos de prueba · diagnostico-SKILL.md

> Archivo de verificación del skill de diagnóstico previo.
> Cada caso contiene: (a) un escrito de prueba ficticio y (b) el diagnóstico esperado completo.
> Uso: pegar el escrito de prueba en una sesión con `diagnostico-SKILL.md` cargado
> y comparar el output del sistema con el diagnóstico esperado.
> Si el output difiere materialmente del esperado: revisar el skill o el perfil de área.
>
> Los escritos son ficticios. Ningún dato identifica a personas o expedientes reales.
> Tres casos: uno laboral, uno civil (daños), uno societario (revisión de contrato).

---

## Cómo usar estos casos

1. Cargar `diagnostico-SKILL.md` + el perfil de área correspondiente.
2. Escribir: "Diagnosticá este escrito" y pegar el texto del caso.
3. Comparar el output del sistema con el "Diagnóstico esperado" del caso.
4. Para cada sección del diagnóstico, verificar:
   - ¿El sistema detectó los mismos problemas?
   - ¿Usó los marcadores canónicos del glosario?
   - ¿No agregó jurisprudencia inventada?
   - ¿No corrigió el escrito sin esperar instrucción?

**Tolerancia de variación:** el diagnóstico esperado es una referencia, no un output exacto.
El sistema puede identificar problemas adicionales no listados aquí: eso es correcto.
El problema es si no detecta alguno de los listados, o si inventa jurisprudencia o normas.

---

## Caso 1 - Laboral · Demanda por despido sin causa

### Escrito de prueba

```
SEÑOR JUEZ NACIONAL DEL TRABAJO:

JUAN PÉREZ, DNI 25.000.000, con domicilio en Av. Corrientes 1234, CABA, con el
patrocinio letrado del Dr. Carlos García, MP CPACF T° 50 F° 100, constituyendo
domicilio procesal en Lavalle 789, CABA, me presento ante V.S. y respetuosamente
digo:

I. OBJETO

Que vengo a demandar a EMPRESA S.A., CUIT 30-00000000-0, por la suma de $5.000.000
en concepto de indemnización por despido sin causa, preaviso omitido y demás rubros
que se liquidan más abajo, con más intereses y costas.

II. HECHOS

Que el suscripto ingresó a trabajar para la demandada el día 1° de marzo de 2019.
Que cumplía tareas de vendedor. Que el día 15 de junio de 2024 fue despedido sin
causa por telegrama. Que la demandada no abonó las indemnizaciones correspondientes.

III. DERECHO

El despido sin causa obliga al empleador a abonar la indemnización del artículo 245
de la LCT. La falta de pago de las indemnizaciones en tiempo y forma hace procedente
el agravante del artículo 2 de la Ley 25.323. La Cámara Nacional del Trabajo ha
establecido en forma reiterada que la sola intimación del trabajador activa el
agravante mencionado. Los intereses se calculan conforme a la tasa activa del
Banco de la Nación Argentina.

IV. LIQUIDACIÓN

- Antigüedad: 5 años y 3 meses
- Mejor remuneración: $800.000
- Indemnización art. 245: $800.000 x 6 = $4.800.000
- Preaviso: $800.000
- SAC sobre preaviso: $66.666
- Art. 2 Ley 25.323 (50%): $2.833.333
- Total: $8.499.999

V. PRUEBA

Testimonial, documental, informativa.

VI. PETITORIO

Por lo expuesto, solicito:
1. Se tenga por presentada la demanda.
2. Se condene a la demandada al pago de $8.499.999.
3. Se impongan las costas a la demandada.
4. Se regulen honorarios.

Proveer de conformidad. SERÁ JUSTICIA.
```

### Diagnóstico esperado

---

**1. Identificación del escrito**
- Tipo: demanda laboral por despido sin causa
- Rama: derecho del trabajo
- Fuero inferido: fuero nacional del trabajo (CABA)
- Parte: actor (trabajador)

---

**2. Argumentos sin norma de respaldo**

```
[ARG SIN NORMA: "La Cámara Nacional del Trabajo ha establecido en forma reiterada
 que la sola intimación del trabajador activa el agravante" - el argumento es
 incorrecto además de carecer de norma: el art. 2 Ley 25.323 requiere que el
 trabajador haya iniciado acciones judiciales o administrativas, no solo intimado.
 La norma de respaldo correcta es art. 2 Ley 25.323 con su requisito completo.]
```

```
[ARG SIN NORMA: los intereses se calculan a la tasa activa del BNA -
 la tasa aplicable en el fuero laboral la fija el acta CNAT vigente,
 no la tasa activa del BNA. Citar el acta CNAT aplicable al período.]
```

---

**3. Hechos no acreditados**

```
[VACÍO PROBATORIO: mejor remuneración de $800.000 - no se indica fuente
 (recibos de sueldo, CCT). Aportar los tres últimos recibos del período
 de cómputo y el CCT aplicable para verificar el tope del art. 245.]
```

```
[VACÍO PROBATORIO: CCT aplicable a la actividad de vendedor - no se indica
 el convenio colectivo. El tope del art. 245 depende del CCT. Sin este dato
 el cálculo es incompleto. Verificar actividad principal del empleador.]
```

```
[VACÍO PROBATORIO: cumplimiento del SECLO - no se menciona si se agotó la
 instancia de conciliación obligatoria previa (Ley 24.635). En el fuero nacional
 del trabajo es requisito de admisibilidad. Aportar certificado del SECLO.]
```

```
[VACÍO PROBATORIO: intimación fehaciente previa al agravante del art. 2
 Ley 25.323 - no se menciona si el trabajador intimó al empleador y si
 debió iniciar acciones. Sin acreditar estos presupuestos, el agravante
 no procede. Aportar telegrama de intimación y acreditación de inicio
 de acciones.]
```

---

**4. Citas jurisprudenciales no verificadas**

```
[JURISPRUDENCIA NO VERIFICADA] "La Cámara Nacional del Trabajo ha establecido
 en forma reiterada que la sola intimación del trabajador activa el agravante"
 - no se cita sala, expediente ni carátula. Reemplazar por:
 [INSERTAR FALLO VERIFICADO: sala CNAT - doctrina sobre presupuestos del art. 2 Ley 25.323]
```

Nota adicional: la doctrina atribuida a la CNAT parece incorrecta. El art. 2 Ley 25.323
requiere inicio de acciones judiciales o administrativas, no solo intimación. Verificar
antes de incluir este argumento.

---

**5. Peticiones sin desarrollo en fundamentos**

```
[PETICIÓN SIN FUNDAMENTO: "Se regulen honorarios" - no hay desarrollo sobre
 la base regulatoria ni el porcentaje aplicable. Agregar en fundamentos
 referencia a la ley arancelaria aplicable.]
```

---

**6. Contradicciones internas**

```
[CONTRADICCIÓN: la liquidación multiplica $800.000 x 6 años = $4.800.000, pero
 la antigüedad indicada es "5 años y 3 meses" / el multiplicador correcto
 según art. 245 LCT (fracción mayor a 3 meses = año completo) es 6 años,
 lo que coincide con el cálculo. Sin embargo, el ingreso declarado es
 1° de marzo de 2019 y el despido el 15 de junio de 2024: eso da 5 años
 y 3 meses, que redondea a 6 años. El multiplicador es correcto pero
 la sección "Antigüedad" debería decir "6 años (con redondeo)" para
 evitar confusión. Resolución: corregir la descripción de antigüedad.]
```

```
[CONTRADICCIÓN: el art. 2 Ley 25.323 se aplica sobre "arts. 232, 233 y 245"
 (preaviso + integración + indemnización). La liquidación calcula el 50%
 sobre ($4.800.000 + $800.000) = $2.800.000, pero incluye el SAC sobre
 preaviso ($66.666) en la base. El SAC sobre preaviso no integra la base
 del agravante. Resolución: recalcular el agravante sobre $5.600.000 x 50%
 = $2.800.000, sin incluir el SAC.]
```

---

**7. Normas con verificación pendiente**

```
[VERIFICAR VIGENCIA] LCT art. 245 - post-DNU 70/2023
[VERIFICAR VIGENCIA] Ley 25.323 art. 2
[VERIFICAR TASA VIGENTE: CNAT - acta aplicable al período del despido]
[VERIFICAR CCT APLICABLE: actividad del empleador - tope art. 245 al momento del despido]
[VERIFICAR MONTO ACTUALIZADO: tope art. 245 - CCT y promedio INDEC al período]
```

---

**8. Observaciones estructurales**

La demanda no ofrece la prueba con el detalle mínimo exigible en el fuero nacional:
no hay descripción de los documentos a ofrecer ni datos de los testigos (nombre,
domicilio, hechos sobre los que declararán). El fuero laboral nacional exige
ofrecer toda la prueba en la demanda; la omisión puede generar dificultades
para ampliarla después.

El escrito no menciona la integración del mes de despido. El despido fue el 15 de junio
de 2024, no el último día del mes: corresponde verificar si procede la integración
(art. 233 LCT [VERIFICAR VIGENCIA]) y si fue incluida en la liquidación.

Los certificados del art. 80 LCT no se mencionan. Si no fueron entregados y el
trabajador intimó, es un rubro adicional de tres salarios. Verificar con el abogado.

---

**9. Síntesis**

9 marcadores emitidos: 2 argumentos sin norma, 4 vacíos probatorios, 1 cita
no verificada, 1 petición sin fundamento, 2 contradicciones internas,
5 normas con verificación pendiente.

El escrito requiere revisión sustancial antes de presentar. Los problemas más
urgentes son: (a) el presupuesto del art. 2 Ley 25.323 está mal planteado
y puede hacer caer ese rubro; (b) el SECLO no está acreditado y puede frustrar
la admisibilidad; (c) el tope del art. 245 no fue verificado contra el CCT
aplicable, lo que puede modificar el cálculo completo.

---

*Diagnóstico completo. ¿Procedemos con las correcciones, o querés revisar algún punto primero?*

---

## Caso 2 - Civil · Escrito de demanda por daños (mala praxis médica)

### Escrito de prueba

```
SEÑOR JUEZ NACIONAL EN LO CIVIL:

MARÍA RODRÍGUEZ, DNI 30.000.000, con domicilio en Belgrano 456, CABA,
con patrocinio letrado, me presento y digo:

I. OBJETO

Vengo a interponer demanda por daños y perjuicios contra el Dr. ROBERTO
LÓPEZ, médico, y contra CLÍNICA BUENOS AIRES S.A., por la mala praxis
cometida en mi cirugía del 10 de marzo de 2022, reclamando la suma de
$50.000.000.

II. HECHOS

Que el 10 de marzo de 2022 fui intervenida quirúrgicamente por el Dr. López
en la Clínica Buenos Aires S.A. Que a raíz de la intervención sufrí graves
secuelas neurológicas. Que la negligencia del médico es evidente.

III. DERECHO

La responsabilidad médica se rige por las normas del Código Civil y Comercial.
El médico responde por su negligencia. La clínica responde solidariamente
por el hecho de su dependiente. Los daños sufridos son de carácter permanente
e irreversibles según la pericia médica adjunta. Corresponde indemnizar el
daño moral, el daño físico y el lucro cesante.

IV. MONTO

El total reclamado es de $50.000.000 distribuido en: daño físico $20.000.000,
daño moral $20.000.000, lucro cesante $10.000.000.

V. PETITORIO

1. Se admita la demanda.
2. Se condene a los demandados al pago de $50.000.000.
3. Con costas.
```

### Diagnóstico esperado

---

**1. Identificación del escrito**
- Tipo: demanda por daños y perjuicios (responsabilidad médica)
- Rama: derecho civil / responsabilidad profesional
- Fuero inferido: fuero nacional civil (CABA)
- Parte: actora

---

**2. Argumentos sin norma de respaldo**

```
[ARG SIN NORMA: "La responsabilidad médica se rige por las normas del
 Código Civil y Comercial" - correcto pero incompleto. Citar específicamente:
 art. 1768 CCCN (responsabilidad del profesional liberal), art. 1753 CCCN
 (responsabilidad del principal por el dependiente para la clínica),
 y arts. 1721-1725 CCCN (factor de atribución).]
```

```
[ARG SIN NORMA: "El médico responde por su negligencia" - no se cita el
 factor de atribución aplicable (culpa, art. 1724 CCCN) ni se desarrolla
 en qué consistió la negligencia. La mera afirmación no es argumento.]
```

```
[ARG SIN NORMA: "La clínica responde solidariamente" - el CCCN distingue
 responsabilidad concurrente (art. 1751) de solidaria (art. 827 y ss.).
 En la responsabilidad del principal por el dependiente (art. 1753 CCCN)
 la responsabilidad es concurrente, no solidaria en sentido estricto.
 Verificar el encuadre antes de usar el término "solidaria".]
```

```
[ARG SIN NORMA: "Corresponde indemnizar el daño moral, el daño físico
 y el lucro cesante" - citar arts. 1738-1741 CCCN para cada rubro.
 El "daño físico" no es una categoría legal en el CCCN; el rubro
 correcto es "incapacidad sobreviniente" (art. 1746 CCCN) o
 "daño a la integridad psicofísica". Reformular.]
```

---

**3. Hechos no acreditados**

```
[VACÍO PROBATORIO: negligencia del médico - el escrito dice que
 "la negligencia es evidente" sin describir en qué consistió el
 desvío del estándar de cuidado. La mala praxis requiere acreditar
 que el médico no actuó con la diligencia del buen profesional
 (art. 1768 CCCN). Aportar: historia clínica completa, protocolo
 quirúrgico, y consulta previa con médico especialista sobre
 si hubo desvío del estándar.]
```

```
[VACÍO PROBATORIO: "pericia médica adjunta" - no se aportó ningún
 archivo con la pericia en esta sesión. Si la pericia existe,
 aportarla para que el sistema pueda analizar su contenido.
 Si no existe aún, la referencia a ella en el escrito es prematura.]
```

```
[VACÍO PROBATORIO: porcentaje de incapacidad sobreviniente -
 para calcular la indemnización por incapacidad (art. 1746 CCCN)
 se necesita el porcentaje determinado por pericia médica.
 Sin este dato el monto de $20.000.000 por "daño físico" carece
 de sustento verificable.]
```

```
[VACÍO PROBATORIO: ingresos de la actora para el lucro cesante -
 no se indica ocupación, remuneración ni cómo se calcularon
 los $10.000.000 reclamados por este rubro. Aportar recibos
 de sueldo o declaraciones impositivas.]
```

```
[VACÍO PROBATORIO: historia clínica - no se menciona si fue
 obtenida. Es el documento central de la causa. Sin ella
 no hay prueba de los hechos ni base para la pericia.
 Verificar si fue requerida formalmente (art. 14 Ley 26.529).]
```

---

**4. Citas jurisprudenciales no verificadas**

Sin citas jurisprudenciales en el escrito. Se requieren para fundar
la cuantificación de daños:

```
[INSERTAR FALLO VERIFICADO: sala CNAC - criterio de cuantificación
 de daño moral en casos de mala praxis con secuelas neurológicas]
```

```
[INSERTAR FALLO VERIFICADO: sala CNAC - fórmula de cuantificación
 de incapacidad sobreviniente aplicada por la sala]
```

---

**5. Peticiones sin desarrollo en fundamentos**

```
[PETICIÓN SIN FUNDAMENTO: "Se admita la demanda" - petición procesal
 válida pero no requiere desarrollo. Sin observación sustancial.]
```

```
[PETICIÓN SIN FUNDAMENTO: $50.000.000 distribuidos en tres rubros -
 ninguno de los tres montos tiene cálculo ni fundamento en la
 sección III. El daño moral no tiene base jurisprudencial citada;
 el daño físico no tiene porcentaje de incapacidad ni fórmula;
 el lucro cesante no tiene base de ingresos ni período de cálculo.
 Desarrollar la cuantificación de cada rubro en fundamentos.]
```

---

**6. Contradicciones internas**

Sin contradicciones internas detectadas.

---

**7. Normas con verificación pendiente**

```
[VERIFICAR VIGENCIA] CCCN art. 1768 - responsabilidad profesional
[VERIFICAR VIGENCIA] CCCN art. 1746 - incapacidad sobreviniente
[VERIFICAR VIGENCIA] CCCN art. 1741 - daño extrapatrimonial
[VERIFICAR VIGENCIA] CCCN art. 1753 - responsabilidad del principal
[VERIFICAR VIGENCIA] CCCN art. 1751 - responsabilidad concurrente
[VERIFICAR VIGENCIA] Ley 26.529 art. 14 - derecho a la historia clínica
[VERIFICAR TASA VIGENTE: fuero civil CABA - acordada CNAC]
[VERIFICAR CRITERIO DEL FUERO: fórmula de cuantificación de incapacidad sobreviniente - sala CNAC actuante]
[VERIFICAR CRITERIO DEL FUERO: daño psicológico autónomo o subsumido en daño moral - fuero civil CABA]
```

---

**8. Observaciones estructurales**

El escrito no ofrece prueba. En el fuero civil la prueba debe ofrecerse en la
demanda: peritos propuestos, documentos a acompañar, testigos con nombre y domicilio,
informes a requerir. La omisión total de este capítulo es un problema de estructura grave.

El escrito no menciona la prescripción: el hecho es del 10 de marzo de 2022 y la
demanda fue redactada en 2025. El plazo de prescripción de la acción resarcitoria
es de 3 años (art. 2561 CCCN [VERIFICAR VIGENCIA]) desde que el damnificado conoció
el daño. Verificar si la prescripción corrió y si hay causal de suspensión.

No se menciona si la clínica tiene aseguradora. Si la hay, la citación en garantía
(art. 118 Ley 17.418 [VERIFICAR VIGENCIA]) protege al actor frente a una eventual
insolvencia del demandado.

---

**9. Síntesis**

14 marcadores emitidos: 4 argumentos sin norma, 5 vacíos probatorios, 2 fallos
requeridos, 1 petición sin fundamento, 9 normas con verificación pendiente,
3 observaciones estructurales graves.

El escrito no está en condiciones de presentarse. Tres problemas urgentes antes
de cualquier otra corrección: (a) verificar prescripción — si ya corrieron
3 años sin suspensión, la demanda está extinguida; (b) obtener la historia
clínica y la pericia antes de radicar, ya que sin ellas no hay prueba del
hecho central; (c) desarrollar la cuantificación de cada rubro con base
concreta o el juez puede tener por no probados los daños por falta de sustento.

---

*Diagnóstico completo. ¿Procedemos con las correcciones, o querés revisar algún punto primero?*

---

## Caso 3 - Societario · Revisión de cláusula de un pacto de accionistas

### Escrito de prueba

```
PACTO DE ACCIONISTAS - CLÁUSULAS PARA REVISIÓN

Cláusula 5 - Derecho de preferencia

En caso de que cualquiera de los accionistas (el "Vendedor") desee transferir
la totalidad o parte de sus acciones a un tercero, los demás accionistas
(los "Beneficiarios") tendrán un derecho de preferencia para adquirir dichas
acciones en igualdad de condiciones con el tercero. El Vendedor deberá notificar
a los Beneficiarios con 30 días de anticipación. Si los Beneficiarios no ejercen
su derecho en dicho plazo, el Vendedor podrá transferir las acciones al tercero
por cualquier precio y en cualquier condición.

Cláusula 6 - Drag Along

El accionista mayoritario (el "Controlante") tendrá el derecho de obligar a los
demás accionistas (los "Arrastrados") a vender la totalidad de sus acciones a un
tercero adquirente en los mismos términos y condiciones que el Controlante.
Este derecho podrá ejercerse en cualquier momento y sin restricciones.

Cláusula 12 - Ley aplicable y jurisdicción

El presente pacto se regirá por las leyes del Estado de Delaware, Estados Unidos,
y cualquier controversia será resuelta por los tribunales de dicho Estado, con
renuncia expresa de las partes a cualquier otro foro.
```

### Diagnóstico esperado

---

**1. Identificación del escrito**
- Tipo: cláusulas de pacto de accionistas (para revisión parcial)
- Rama: derecho societario
- Fuero inferido: no determinable del texto (depende de jurisdicción de inscripción)
- Parte: no determinable (el pacto involucra a todos los accionistas)

Nota: el sistema solo recibió tres cláusulas, no el pacto completo. El análisis
puede ser incompleto por falta de contexto. Se advierte al abogado antes de proceder.

---

**2. Argumentos sin norma de respaldo**

No hay argumentos jurídicos en el texto; son cláusulas contractuales.
Se aplica análisis de red-flags en lugar de este bloque.

---

**3. Hechos no acreditados**

```
[VACÍO PROBATORIO: estatuto/contrato social no aportado - las cláusulas del
 pacto de accionistas deben ser analizadas en articulación con el estatuto.
 En particular: si la cláusula 5 de ROFR está también en el estatuto (para
 ser oponible a la sociedad) o solo en el pacto (solo vincula a los firmantes).
 Aportar el estatuto o contrato social para el análisis completo.]
```

---

**4. Citas jurisprudenciales no verificadas**

Sin citas jurisprudenciales. Se requieren para evaluar la ejecutabilidad del drag-along:

```
[INSERTAR FALLO VERIFICADO: sala CNACOM - ejecutabilidad de cláusula drag-along
 en pacto de accionistas sin precio mínimo garantizado]
```

---

**5. Red-flags detectadas**

```
[RED FLAG - NULIDAD ABSOLUTA: cláusula 12 - ley aplicable Delaware y prórroga
 de jurisdicción a tribunales del Estado de Delaware - norma: art. 2654 CCCN
 [VERIFICAR VIGENCIA]. Si alguno de los accionistas es consumidor, la prórroga
 es inválida de pleno derecho. Incluso entre no consumidores: las sociedades
 argentinas inscriptas en IGPJ Córdoba/IGJ tienen vínculos con el ordenamiento argentino
 que pueden tornar inaplicable la prórroga en aspectos de derecho societario
 (arts. 118-124 LGS [VERIFICAR VIGENCIA]). Verificar con el abogado si la
 prórroga es válida para el tipo de controversia que se prevé.]
```

```
[RED FLAG - RIESGO ALTO: cláusula 6 (drag-along) - el derecho de arrastre
 puede ejercerse "en cualquier momento y sin restricciones". Ausencia de:
 (a) precio mínimo garantizado para los arrastrados, (b) notificación previa
 con plazo razonable, (c) condición de que el adquirente sea un tercero de
 buena fe. Una cláusula de drag-along sin precio mínimo puede configurar
 abuso del derecho de control (art. 10 CCCN [VERIFICAR VIGENCIA] y art. 54
 LGS [VERIFICAR VIGENCIA]). Propuesta de redacción alternativa: agregar
 precio mínimo igual al valor resultante de la metodología de valuación
 pactada en el pacto, notificación previa de 30 días, y posibilidad del
 arrastrado de impugnar el precio si no responde a la metodología pactada.]
```

```
[RED FLAG - RIESGO MEDIO: cláusula 5 (ROFR) - si los Beneficiarios no ejercen
 el derecho, el Vendedor puede transferir "por cualquier precio y en cualquier
 condición". Esto elimina efectivamente el derecho de preferencia como
 protección: el tercero adquirente podría pagar un precio irrisorio sin que
 los Beneficiarios puedan objetarlo. Considerar agregar que la transferencia
 al tercero no puede hacerse en condiciones más favorables que las notificadas
 a los Beneficiarios durante el período de ejercicio.]
```

---

**6. Peticiones sin desarrollo en fundamentos**

No aplica (es un contrato, no un escrito judicial).

---

**7. Contradicciones internas**

```
[CONTRADICCIÓN: la cláusula 5 fija un plazo de 30 días para que los
 Beneficiarios ejerzan el derecho de preferencia / la cláusula 6 permite
 al Controlante ejercer el drag-along "en cualquier momento y sin
 restricciones". Si el Controlante activa el drag-along durante el período
 de 30 días del ROFR de un Beneficiario, no queda claro qué derecho prevalece.
 Resolución necesaria: definir jerarquía entre ambas cláusulas o establecer
 que el drag-along solo opera una vez vencido el plazo de ejercicio del ROFR.]
```

---

**8. Normas con verificación pendiente**

```
[VERIFICAR VIGENCIA] CCCN art. 2654 - prórroga de jurisdicción al extranjero
[VERIFICAR VIGENCIA] CCCN art. 10 - abuso del derecho
[VERIFICAR VIGENCIA] LGS art. 54 - inoponibilidad de la personalidad jurídica / abuso de control
[VERIFICAR VIGENCIA] LGS arts. 118-124 - sociedades extranjeras y ley aplicable
[VERIFICAR RESOLUCIÓN REGISTRAL VIGENTE: IGJ/IGPJ Córdoba - oponibilidad de pactos de accionistas]
```

---

**9. Observaciones estructurales**

El pacto fue aportado solo parcialmente (tres cláusulas de doce o más).
El análisis de oponibilidad frente a la sociedad y la interacción con otras
cláusulas del pacto no puede hacerse sin el texto completo. En particular,
falta la cláusula de valuación (crítica para evaluar el drag-along) y las
cláusulas de gobierno corporativo.

---

**9. Síntesis**

10 marcadores emitidos: 1 vacío probatorio, 1 fallo requerido, 1 red flag de
nulidad absoluta, 1 red flag de riesgo alto, 1 red flag de riesgo medio,
1 contradicción interna, 5 normas con verificación pendiente.

El problema más urgente es la cláusula 12: si la sociedad está inscripta en
Argentina, la prórroga a Delaware puede ser inoponible en aspectos de derecho
societario con independencia de lo que acuerden los accionistas. Antes de firmar,
el abogado debe definir si la controversia que se anticipa es societaria (donde
aplica LGS) o puramente contractual entre los accionistas (donde la prórroga
puede tener más margen). Esta distinción cambia la solución.

---

*Diagnóstico completo. ¿Procedemos con las correcciones, o querés revisar algún punto primero?*

---

## Notas de mantenimiento

Actualizar estos casos cuando:
- Cambie la estructura de secciones del `diagnostico-SKILL.md`
- Se modifiquen los marcadores canónicos en `marcadores-GLOSARIO.md`
- Un cambio normativo relevante afecte el análisis esperado (por ejemplo,
  si cambia el plazo de prescripción de la acción resarcitoria civil o
  el presupuesto del art. 2 Ley 25.323)
- Se detecte que el sistema consistentemente omite un tipo de problema
  que los casos de prueba deberían capturar

Registrar cualquier actualización en `CHANGELOG.md`.

---

*Última actualización: mayo 2026*
*Autor: Dr. Cristian Aboitiz · [@abogadoaboitiz](https://x.com/abogadoaboitiz)*
