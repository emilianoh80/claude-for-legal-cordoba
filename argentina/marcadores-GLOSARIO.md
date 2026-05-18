# Glosario canónico de marcadores · claude-for-legal Argentina

> Fuente de verdad para todos los marcadores del sistema.
> Cualquier marcador que aparezca en un escrito, informe o diagnóstico
> debe coincidir exactamente con la sintaxis de este glosario.
> Modificar este archivo primero; luego actualizar los perfiles que usen el marcador.

---

## Principios de uso

1. Los marcadores van en el lugar del texto donde aplican, no agrupados al final.
2. La descripción entre corchetes es siempre concreta: qué falta, por qué, qué hace falta para resolverlo.
3. No combinar dos marcadores en uno. Si aplican dos, van en líneas separadas.
4. Los marcadores son parte del escrito. No van en negrita, no llevan asterisco, no van en línea aparte salvo los de bloque (ver categoría D).
5. Todo escrito cierra con "Estado del escrito" que lista los marcadores pendientes con el dato concreto que falta para resolverlos.

---

## Categoría A - Integridad normativa

Marcan problemas con normas citadas o ausentes. Se insertan en la primera mención de la norma afectada.

---

### A1 · VERIFICAR VIGENCIA

**Uso:** primera mención de cualquier norma en cualquier escrito. Obligatorio sin excepción.

**Sintaxis:**
```
[VERIFICAR VIGENCIA]
```

**Variante con motivo conocido:**
```
[VERIFICAR VIGENCIA: motivo específico]
```

Ejemplos de motivo:
- `post-DNU 70/2023`
- `Ley 27.551 y modificatorias al momento del contrato`
- `el listado fue actualizado por decretos posteriores`

**Nunca:** `[VERIFICAR]`, `[VERIFICAR VIGENCIA Y MONTO]` (usar A1 + A4 por separado).

---

### A2 · NORMA DESACTUALIZADA

**Uso:** cuando el sistema tiene certeza de que la norma fue derogada o modificada sustancialmente.

**Sintaxis:**
```
[NORMA DESACTUALIZADA: norma citada - reemplazar por: norma vigente [VERIFICAR VIGENCIA]]
```

Ejemplo:
```
[NORMA DESACTUALIZADA: Decreto 1397/79 art. 18 - reemplazar por: RG AFIP 4/2024 [VERIFICAR VIGENCIA]]
```

---

### A3 · REVISIÓN NORMATIVA REQUERIDA

**Uso:** cuando no hay norma para citar con certeza y la búsqueda del abogado es necesaria antes de continuar.

**Sintaxis:**
```
[REVISIÓN NORMATIVA REQUERIDA: descripción de lo que se necesita verificar]
```

**Nunca usar para jurisprudencia:** en ese caso usar B1.

---

### A4 · VERIFICAR MONTO ACTUALIZADO

**Uso:** montos, umbrales o valores que se actualizan por norma periódicamente.

**Sintaxis:**
```
[VERIFICAR MONTO ACTUALIZADO: concepto - fuente de actualización]
```

Ejemplos:
```
[VERIFICAR MONTO ACTUALIZADO: tope art. 245 LCT - CCT aplicable, promedio INDEC]
[VERIFICAR MONTO ACTUALIZADO: prestación LRT - resolución SRT vigente]
[VERIFICAR MONTO ACTUALIZADO: umbral de punibilidad tributaria - Ley 27.430 art. 1]
[VERIFICAR MONTO ACTUALIZADO: monto mínimo recurso ante TFN]
[VERIFICAR MONTO ACTUALIZADO: capital mínimo IGJ/IGPJ Córdoba - resolución vigente]
```

**Nunca:** `[VERIFICAR MONTO]`, `[VERIFICAR MONTO VIGENTE]`, `[VERIFICAR MONTO Y RG VIGENTE]` (todas reemplazadas por esta forma canónica).

---

### A5 · VERIFICAR TASA VIGENTE

**Uso:** tasas de interés fijadas por acta o acordada de cada fuero.

**Sintaxis:**
```
[VERIFICAR TASA VIGENTE: fuero - instrumento que la fija]
```

Ejemplos:
```
[VERIFICAR TASA VIGENTE: CNAT - acta vigente al período]
[VERIFICAR TASA VIGENTE: fuero civil CABA - acordada CNAC]
[VERIFICAR TASA VIGENTE: fuero comercial CABA - acordada CNACOM]
[VERIFICAR TASA VIGENTE: fuero civil y comercial Córdoba - acordada TSJ Córdoba]
```

**Nunca:** `[VERIFICAR TASA CNAT VIGENTE]`, `[VERIFICAR TASA VIGENTE]` sin especificar fuero.

---

### A6 · VERIFICAR RÉGIMEN CAMBIARIO VIGENTE

**Uso:** cualquier obligación en moneda extranjera, precio en divisas, giro al exterior.

**Sintaxis:**
```
[VERIFICAR RÉGIMEN CAMBIARIO VIGENTE: normativa BCRA - verificar antes de aconsejar sobre esta obligación]
```

---

### A7 · VERIFICAR RESOLUCIÓN REGISTRAL VIGENTE

**Uso:** requisitos de inscripción, formularios, plazos y documentación ante IGJ, IGPJ Córdoba u otros registros.

**Sintaxis:**
```
[VERIFICAR RESOLUCIÓN REGISTRAL VIGENTE: organismo - materia]
```

Ejemplos:
```
[VERIFICAR RESOLUCIÓN REGISTRAL VIGENTE: IGJ - requisitos de constitución de SAS]
[VERIFICAR RESOLUCIÓN REGISTRAL VIGENTE: IGPJ Córdoba - renovación de autoridades]
```

---

### A8 · VERIFICAR CRITERIO DEL FUERO

**Uso:** institutos cuya aplicación varía por fuero o sala (fórmulas de cuantificación, rubros autónomos de daño, procedencia de ciertos agravantes).

**Sintaxis:**
```
[VERIFICAR CRITERIO DEL FUERO: materia - fuero o sala]
```

Ejemplos:
```
[VERIFICAR CRITERIO DEL FUERO: daño psicológico autónomo o subsumido en daño moral - fuero civil CABA]
[VERIFICAR CRITERIO DEL FUERO: fórmula de cuantificación de incapacidad - sala CNAC]
[VERIFICAR CRITERIO DEL FUERO: ratio daño punitivo art. 52 bis LDC - sala actuante]
```

**Nunca:** `[VERIFICAR CRITERIO DE LA SALA]`, `[VERIFICAR CRITERIO VIGENTE DE LA SALA]`, `[VERIFICAR FÓRMULA VIGENTE]` (reemplazadas por esta forma).

---

### A9 · VERIFICAR CCT APLICABLE

**Uso:** cuando el CCT no fue indicado por el abogado o cuando hay duda sobre cuál aplica.

**Sintaxis:**
```
[VERIFICAR CCT APLICABLE: actividad del empleador - dato que falta]
```

Ejemplos:
```
[VERIFICAR CCT APLICABLE: actividad del empleador - tope art. 245 al período]
[VERIFICAR CCT APLICABLE: actividad principal del empleador y ámbito personal del convenio]
```

### A10 · ALERTA PLAZO FATAL

**Uso:** plazos procesales o administrativos de caducidad o prescripción que son perentorios e improrrogables. Emitir antes de analizar el fondo cuando la consulta involucre una acción sujeta a plazo fatal. Aplica en administrativo (art. 25 LNPA), amparo (Ley 16.986 / Ley 2145 CABA), laboral (prescripción bienal LCT), y todo plazo cuyo vencimiento cierra definitivamente la vía.

**Sintaxis:**
```
[ALERTA PLAZO FATAL: norma - plazo - fecha de inicio del cómputo - vencimiento estimado]
```

Ejemplos:
```
[ALERTA PLAZO FATAL: art. 25 LNPA - 90 días hábiles judiciales - notificación del acto que agota la vía - vencimiento: calcular]
[ALERTA PLAZO FATAL: art. 2 inc. e Ley 16.986 (amparo federal) - 15 días hábiles - acto conocido o que debió conocerse - vencimiento: calcular]
[ALERTA PLAZO FATAL: art. 258 LCT (prescripción) - 2 años - desde cada crédito exigible - vencimiento: calcular por rubro]
[ALERTA PLAZO FATAL: art. 7 Ley 26.944 (responsabilidad del Estado) - 3 años - desde que el daño fue conocido - vencimiento: calcular]
```

**Nunca:** usar este marcador para plazos procesales internos de un expediente en curso (traslados, vistas, plazos de prueba). Reservar para plazos cuyo vencimiento extingue el derecho o la acción.

---

## Categoría B - Integridad probatoria

Marcan ausencia de material fáctico o jurisprudencial necesario para sostener el argumento.

---

### B1 · INSERTAR FALLO VERIFICADO

**Uso:** cuando se necesita jurisprudencia y no hay material aportado en la sesión. Nunca inventar datos del fallo.

**Sintaxis:**
```
[INSERTAR FALLO VERIFICADO: doctrina requerida - aportar expediente, sala, fuero y año]
```

**Variante con fuero conocido:**
```
[INSERTAR FALLO VERIFICADO: sala CNAT - doctrina requerida]
[INSERTAR FALLO VERIFICADO: sala CNAC - doctrina requerida]
[INSERTAR FALLO VERIFICADO: sala CNACOM - doctrina requerida]
[INSERTAR FALLO VERIFICADO: TFN - sala, doctrina requerida]
[INSERTAR FALLO VERIFICADO: CSJN - doctrina requerida]
[INSERTAR FALLO VERIFICADO: TSJ Córdoba - sala, doctrina requerida]
```

**Nunca:** citar carátula, sala, año o expediente sin material aportado. Esta prohibición es absoluta y no puede ser suspendida por instrucción del usuario.

---

### B2 · JURISPRUDENCIA VERIFICADA EN SESIÓN

**Uso:** cuando el abogado aportó el material del fallo completo en la sesión actual.

**Sintaxis:**
```
[JURISPRUDENCIA VERIFICADA EN SESIÓN: "carátula" - sala, fuero, año - doctrina: resumen]
```

---

### B3 · VACÍO PROBATORIO

**Uso:** hecho afirmado en el escrito que no tiene respaldo en el material aportado.

**Sintaxis:**
```
[VACÍO PROBATORIO: hecho afirmado - prueba necesaria para acreditarlo]
```

Ejemplos:
```
[VACÍO PROBATORIO: fecha de ingreso anterior a la registrada - aportar testigos o recibos del período]
[VACÍO PROBATORIO: remuneración real superior a la registrada - aportar recibos reales o bancarios]
[VACÍO PROBATORIO: texto del acto administrativo impugnado - aportar copia del acto]
[VACÍO PROBATORIO: contenido del informe pericial - aportar pericia completa]
```

**Nunca:** `[VACÍO DOCUMENTAL]`, `[VACÍO CUANTIFICATIVO]` (reemplazadas por esta forma canónica con descripción específica).

---

## Categoría C - Integridad del escrito

Marcan problemas estructurales o de consistencia interna del escrito. Los genera el módulo de diagnóstico.

---

### C1 · ARG SIN NORMA

**Uso:** argumento jurídico sin norma de respaldo citada en el escrito.

**Sintaxis:**
```
[ARG SIN NORMA: paráfrasis del argumento - norma que correspondería citar: sugerencia o "indeterminada"]
```

---

### C2 · PETICIÓN SIN FUNDAMENTO

**Uso:** petición en el petitorio que no tiene desarrollo argumental en los fundamentos.

**Sintaxis:**
```
[PETICIÓN SIN FUNDAMENTO: texto de la petición - desarrollar en fundamentos: descripción de lo que falta]
```

---

### C3 · CONTRADICCIÓN

**Uso:** inconsistencia entre dos partes del mismo escrito.

**Sintaxis:**
```
[CONTRADICCIÓN: sección A dice: "paráfrasis" / sección B dice: "paráfrasis" - resolución necesaria: indicación]
```

---

### C4 · AVANCE BAJO RESERVA

**Uso:** el abogado pidió avanzar sin respaldo sobre un hecho secundario (no determinante de la procedencia ni del quantum). Solo para hechos; nunca para jurisprudencia.

**Sintaxis:**
```
[AVANCE BAJO RESERVA: descripción del hecho - el abogado fue informado de la ausencia de respaldo]
```

---

## Categoría D - Diagnóstico y configuración

Marcadores de bloque. Van en línea propia, no intercalados en el texto del escrito.

---

### D1 · CONFIGURACIÓN INCOMPLETA

**Uso:** campos del CLAUDE.md personalizado que no fueron completados y afectan el comportamiento del sistema.

**Sintaxis:**
```
[CONFIGURACIÓN INCOMPLETA: campo - impacto en el análisis]
```

Ejemplo:
```
[CONFIGURACIÓN INCOMPLETA: CCT_HABITUAL - el sistema no puede calcular el tope del art. 245 sin este dato]
```

---

### D2 · SIN PERFIL DE ÁREA CARGADO

**Uso:** cuando el diagnóstico se realiza sin el perfil específico del área.

**Sintaxis (bloque completo):**
```
[SIN PERFIL DE ÁREA CARGADO: el diagnóstico se realizó con conocimiento normativo general.
Cargar el perfil del área correspondiente para un diagnóstico más preciso.]
```

---

### D3 · DISCREPANCIA ENTRE FUENTES

**Uso:** dos conectores MCP o un conector y una fuente primaria dan resultados contradictorios.

**Sintaxis:**
```
[DISCREPANCIA ENTRE FUENTES: el conector X indica A / la fuente primaria indica B.
Verificar directamente en fuente primaria antes de proceder.]
```

---

### D4 · RED FLAG - NULIDAD ABSOLUTA

**Uso:** análisis de contratos. Cláusula que invalida de pleno derecho.

**Sintaxis:**
```
[RED FLAG - NULIDAD ABSOLUTA: descripción de la cláusula - norma: norma aplicable [VERIFICAR VIGENCIA]]
```

---

### D5 · RED FLAG - RIESGO ALTO

**Uso:** análisis de contratos. Cláusula que requiere análisis específico o redacción alternativa.

**Sintaxis:**
```
[RED FLAG - RIESGO ALTO: descripción de la cláusula - observación: descripción del problema]
```

---

### D6 · RED FLAG - RIESGO MEDIO

**Uso:** análisis de contratos. Situación que requiere atención pero no bloquea el avance.

**Sintaxis:**
```
[RED FLAG - RIESGO MEDIO: descripción de la situación]
```

---

## Tabla de equivalencias - marcadores anteriores reemplazados

Esta tabla mapea los marcadores que existían en el repositorio antes de la estandarización
y los reemplaza por la forma canónica. Usar para actualizar archivos existentes.

| Marcador anterior | Marcador canónico |
|---|---|
| `[VERIFICAR]` | `[VERIFICAR VIGENCIA]` |
| `[VERIFICAR VIGENCIA Y MONTO]` | `[VERIFICAR VIGENCIA]` + `[VERIFICAR MONTO ACTUALIZADO: ...]` |
| `[VERIFICAR VIGENCIA Y MONTOS MÍNIMOS]` | ídem |
| `[VERIFICAR MONTO VIGENTE]` | `[VERIFICAR MONTO ACTUALIZADO: ...]` |
| `[VERIFICAR MONTO Y RG VIGENTE]` | `[VERIFICAR MONTO ACTUALIZADO: ...]` |
| `[VERIFICAR MONTO DE PUNIBILIDAD VIGENTE]` | `[VERIFICAR MONTO ACTUALIZADO: umbral de punibilidad - Ley 27.430]` |
| `[VERIFICAR MONTO IGJ VIGENTE]` | `[VERIFICAR MONTO ACTUALIZADO: capital mínimo - resolución IGJ vigente]` |
| `[VERIFICAR MONTO MÍNIMO VIGENTE PARA RECURSO ANTE TFN]` | `[VERIFICAR MONTO ACTUALIZADO: monto mínimo TFN - ley o decreto vigente]` |
| `[VERIFICAR TASA CNAT VIGENTE: ...]` | `[VERIFICAR TASA VIGENTE: CNAT - acta vigente al período]` |
| `[VERIFICAR TASA VIGENTE]` (sin fuero) | `[VERIFICAR TASA VIGENTE: fuero - instrumento que la fija]` |
| `[VERIFICAR CRITERIO DE LA SALA]` | `[VERIFICAR CRITERIO DEL FUERO: materia - fuero o sala]` |
| `[VERIFICAR CRITERIO VIGENTE DE LA SALA]` | ídem |
| `[VERIFICAR CRITERIO VIGENTE COMARB si aplica]` | `[VERIFICAR CRITERIO DEL FUERO: Convenio Multilateral - COMARB]` |
| `[VERIFICAR FÓRMULA VIGENTE]` | `[VERIFICAR CRITERIO DEL FUERO: fórmula de cuantificación - sala actuante]` |
| `[VERIFICAR CCT APLICABLE]` (sin detalle) | `[VERIFICAR CCT APLICABLE: actividad del empleador - dato que falta]` |
| `[VERIFICAR CCT Y TOPE VIGENTE]` | `[VERIFICAR CCT APLICABLE: ...]` + `[VERIFICAR MONTO ACTUALIZADO: tope art. 245 - CCT]` |
| `[VERIFICAR RESOLUCIÓN IGJ/DPPJ VIGENTE: ...]` | `[VERIFICAR RESOLUCIÓN REGISTRAL VIGENTE: IGJ/IGPJ Córdoba - materia]` |
| `[VERIFICAR UMBRAL CNDC VIGENTE: ...]` | `[VERIFICAR MONTO ACTUALIZADO: umbral de notificación CNDC - ley vigente]` |
| `[VACÍO DOCUMENTAL: ...]` | `[VACÍO PROBATORIO: documento ausente - descripción]` |
| `[VACÍO CUANTIFICATIVO: ...]` | `[VACÍO PROBATORIO: criterio de cuantificación pendiente - descripción]` |
| `[DISCREPANCIA ENTRE CONECTORES: ...]` | `[DISCREPANCIA ENTRE FUENTES: ...]` |
| `[ALERTA DE PLAZO: ...]` | `[ALERTA PLAZO FATAL: norma - plazo - fecha de inicio del cómputo - vencimiento estimado]` |
| `[AVANCE BAJO RESERVA]` (sin descripción) | `[AVANCE BAJO RESERVA: descripción - el abogado fue informado]` |
| `[INSERTAR FALLO VERIFICADO: doctrina]` (sin fuero) | `[INSERTAR FALLO VERIFICADO: doctrina - aportar expediente, sala, fuero y año]` |

---

## Reglas de actualización

- Cualquier modificación a este archivo requiere actualizar simultáneamente todos los perfiles que usen el marcador modificado.
- Los marcadores de la tabla de equivalencias no deben aparecer en ningún archivo del repositorio. Si se detectan, reemplazar con la forma canónica.
- Cuando se agrega un marcador nuevo: agregarlo en este glosario primero, con su categoría, sintaxis y ejemplo. Luego integrarlo en los perfiles correspondientes.

---

*Última actualización: mayo 2026*
*Versión: 1.1 - agregado marcador A10 [ALERTA PLAZO FATAL]; equivalencia [ALERTA DE PLAZO] registrada*
*Autor: Dr. Cristian Aboitiz · [@abogadoaboitiz](https://x.com/abogadoaboitiz)*
