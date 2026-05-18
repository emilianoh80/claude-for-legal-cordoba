# Ejemplos · Societario y M&A · Derecho argentino

> Archivo complementario de `societario-CLAUDE.md`.
> Cargar junto con el perfil societario en las instrucciones del Project.
> Cubre due diligence en compraventa de empresas medianas, constitución y
> estructuración de sociedades, y pactos de accionistas bajo LGS y CCCN.
>
> Los ejemplos usan estructuras típicas de práctica PyME y empresa mediana argentina.
> Adaptar el alcance del due diligence al tamaño y la complejidad de la operación.

---

## Advertencia de uso

Los requisitos registrales (IPJ Córdoba / IGJ / registros provinciales) cambian por
resolución sin publicidad amplia. Verificar el estado de trámites y requisitos
en el organismo correspondiente antes de asesorar sobre inscripciones.
La normativa IGJ en particular tiene resoluciones frecuentes que modifican
formularios, plazos y requisitos de documentación.

---

## Ejemplo 1 - Due diligence en compraventa de empresa mediana

### Alcance estándar

El alcance del due diligence depende del precio de la operación, el sector
de actividad y los riesgos identificados en la etapa preliminar. Este checklist
cubre el alcance estándar para una empresa mediana argentina.

### Bloque 1 - Societario y registral

- [ ] Estatuto social vigente y todas sus modificaciones
- [ ] Libro de actas de directorio y asamblea: últimos 5 años
- [ ] Libro de registro de acciones o cuotas partes: titular actual verificado
- [ ] Inscripción vigente ante IPJ Córdoba / IGJ: verificar última renovación de autoridades
- [ ] Poderes vigentes: verificar alcance y si hay poderes revocados no cancelados
- [ ] Sucursales: verificar inscripción si tiene actividad en otras provincias
- [ ] Sociedades vinculadas y controladas: verificar estructura del grupo

**Alertas específicas:**
```
[VERIFICAR VIGENCIA: autoridades inscriptas en IPJ Córdoba/IGJ - contrastar con libro de actas]
[VERIFICAR: si la sociedad tiene más de 2 años sin renovar autoridades, puede haber
 irregularidades que dificulten la inscripción de la transferencia]
```

### Bloque 2 - Laboral

- [ ] Nómina completa de empleados: modalidad contractual, antigüedad, CCT aplicable
- [ ] Registración ante AFIP (F.931): verificar consistencia con nómina real
- [ ] Juicios laborales pendientes: fuero laboral Córdoba + fuero nacional si corresponde
- [ ] CCT aplicable: ¿se paga el salario convencional? ¿hay diferencias pendientes?
- [ ] Pasivos contingentes: estimar liquidaciones eventuales si hay empleados con
      antigüedad alta y salario por encima del tope

**Verificar antes de cuantificar el pasivo laboral:**
```
[VERIFICAR CCT APLICABLE: tope art. 245 al momento de la due diligence]
[VERIFICAR: si hay empleados no registrados o subregistrados, el pasivo potencial
 aumenta con los agravantes de la Ley 24.013 y la Ley 25.323]
```

### Bloque 3 - Impositivo

- [ ] CUIT: estado ante AFIP, categoría, domicilio fiscal
- [ ] Declaraciones juradas de IVA y Ganancias: últimos 3 ejercicios
- [ ] Deudas ante AFIP: certificado de deuda o consulta de estado de cuenta
- [ ] Planes de pago vigentes: verificar cuotas al día y monto pendiente
- [ ] Ingresos brutos: deudas ante DGR / ARCO Córdoba (y/o AGIP si tiene actividad en CABA)
- [ ] Convenio Multilateral: si la empresa tiene actividad multijurisdiccional
- [ ] Juicios de ejecución fiscal pendientes

```
[REVISIÓN NORMATIVA REQUERIDA: verificar si hay reforma tributaria relevante
 posterior al período auditado antes de cuantificar el pasivo impositivo]
```

### Bloque 4 - Contratos y activos

- [ ] Contratos de larga duración: vencimientos, cláusulas de change of control
- [ ] Contratos de locación de inmuebles: vencimiento y condiciones de renovación
- [ ] Propiedad intelectual: marcas, patentes, software - titularidad verificada
- [ ] Licencias de uso de software: verificar que las licencias son transferibles
- [ ] Activos inmuebles: título de propiedad, gravámenes, hipotecas

**Cláusula de change of control:**
Revisar en todos los contratos relevantes si hay cláusula que otorga
derecho de rescisión o renegociación al cocontratante ante cambio de control
de la sociedad. Estas cláusulas pueden frustrar contratos clave post-cierre.

### Bloque 5 - Litigios y pasivos contingentes

- [ ] Juicios civiles y comerciales pendientes: actor y demandado
- [ ] Juicios laborales: ver bloque 2
- [ ] Juicios fiscales: ver bloque 3
- [ ] Medidas cautelares vigentes sobre activos o cuentas bancarias
- [ ] Denuncias penales o investigaciones en curso

**Cuantificación de pasivos contingentes:**

Para cada juicio pendiente:
- Etapa procesal
- Probabilidad de condena (alta / media / baja) - evaluar con el abogado del área
- Monto reclamado vs. monto de condena estimado
- Si hay cobertura de seguro: verificar que aplica y que la aseguradora fue notificada

### Bloque 6 - Bancario y financiero

- [ ] Cuentas bancarias: titularidad y apoderados vigentes
- [ ] Préstamos y créditos: vencimientos, garantías otorgadas
- [ ] Fideicomisos: verificar si la sociedad actúa como fiduciante o fiduciaria
- [ ] Cheques rechazados: consultar base BCRA

---

## Ejemplo 2 - Pacto de accionistas

### Estructura estándar para una empresa mediana con 2 o 3 socios

**Encuadre normativo:**
Los pactos de accionistas son válidos entre las partes bajo el CCCN (libertad
contractual, art. 958 CCCN) pero no son oponibles a la sociedad ni a terceros
si no están incorporados al estatuto. Verificar qué compromisos requieren
modificación estatutaria para ser plenamente ejecutables.

**Cláusulas que generalmente van en el pacto (no en el estatuto):**

#### 1. Directorio y gobierno corporativo

- Composición del directorio: cuántos directores designa cada parte
- Materias reservadas: decisiones que requieren unanimidad o quórum especial
  (endeudamiento sobre cierto monto, adquisición de activos, nuevas líneas de negocio)
- Política de dividendos: criterio de distribución, retención mínima para reinversión

#### 2. Transferencia de participaciones

**Tag along (derecho de adhesión):**
Si un socio vende su participación a un tercero, los demás tienen derecho
a vender en las mismas condiciones. Verificar:
- ¿El tag along es total o parcial (proporcional)?
- ¿Qué precio y condiciones se trasladan?
- Plazo para ejercer el derecho

**Drag along (derecho de arrastre):**
Si el socio mayoritario recibe una oferta de compra del 100% de la empresa,
puede obligar a los minoritarios a vender en las mismas condiciones. Verificar:
- ¿Hay precio mínimo garantizado para el drag along?
- ¿El precio es el mismo que el ofrecido al mayoritario?

**Derecho de preferencia (ROFR):**
Ante una venta, los socios existentes tienen derecho a igualar la oferta del tercero.
```
[VERIFICAR VIGENCIA: LGS art. 153 (SRL) y art. 214 (SA) - las restricciones
 a la transferencia en el estatuto tienen límites legales que el pacto no puede
 exceder si se incorpora al estatuto]
```

**Lock-up:**
Período durante el cual ningún socio puede vender (habitual en los primeros 2-3 años).
Excepciones típicas: muerte, incapacidad, cambio de control de la persona jurídica socia.

#### 3. Valuación de la participación

Crucial para que funcionen el tag along, drag along y el derecho de preferencia.
Opciones más usadas en práctica argentina:

- **Valor de libros ajustado:** simple, predecible, generalmente favorable al comprador
- **EBITDA x múltiplo:** requiere acordar el múltiplo de antemano; verificar
  que se especifica claramente cuál es el EBITDA base (últimos 12 meses, promedio
  de 3 años, proyectado)
- **Valuación por árbitro o perito:** más justo pero más costoso y lento;
  acordar quién lo designa y el plazo

```
[VACÍO PROBATORIO: el método de valuación es el punto que genera más disputas
 societarias en práctica argentina. No dejar esta cláusula en blanco o con
 remisión a "valor de mercado" sin mecanismo de determinación concreto]
```

#### 4. Situaciones de deadlock

Qué pasa cuando los socios no se ponen de acuerdo en una decisión reservada.

Mecanismos frecuentes:
- **Mediación o arbitraje:** plazo para resolver el deadlock; si no se resuelve,
  se activa el siguiente mecanismo
- **Put/call (Texas shootout / Russian roulette):** un socio ofrece un precio;
  el otro elige si compra o vende a ese precio. Equilibra el incentivo de ofrecer
  un precio justo.
- **Liquidación ordenada:** si el deadlock persiste, los socios convienen la venta
  de la empresa o su liquidación

#### 5. No competencia y no solicitud

- Plazo y ámbito geográfico: deben ser razonables para ser válidos (arts. 958, 279 CCCN)
- Penalidad pactada: verificar que no sea desproporcionada (art. 794 CCCN)
- ¿Se extiende a los herederos o solo al firmante?

#### 6. Resolución de conflictos

- Ley aplicable: derecho argentino en todos los casos si las partes son argentinas
  y la sociedad está inscripta en Argentina
- Fuero: verificar si hay prórroga de jurisdicción válida
- Arbitraje: si se pacta arbitraje, especificar institución (CAM, CIAC, AMCA
  u otra), número de árbitros, sede y ley aplicable al procedimiento

**Notas sobre ejecutabilidad del pacto:**
- Las cláusulas del pacto son obligaciones contractuales entre los socios firmantes.
  Si un socio las viola, la consecuencia es la acción por daños y perjuicios, no
  la nulidad del acto societario en sí (a menos que la cláusula esté en el estatuto).
- Para que el tag along, drag along y ROFR sean oponibles a la sociedad,
  deben estar en el estatuto social inscripto. Verificar qué va en el pacto
  y qué requiere modificación estatutaria.

---

## Checklist - constitución de sociedades

Verificar antes de asesorar sobre el tipo societario más adecuado.

**Preguntas previas:**
- [ ] ¿Cuántos socios? ¿Personas humanas o jurídicas?
- [ ] ¿Hay socio extranjero? ¿Requiere autorización para operar en Argentina?
- [ ] ¿Cuál es el objeto? ¿Tiene alguna actividad regulada?
- [ ] ¿La sociedad va a tener empleados desde el inicio?
- [ ] ¿Se prevé incorporar nuevos socios o inversores en el corto plazo?
- [ ] ¿Hay bienes inmuebles a aportar? (impacto impositivo y registral)

**Comparativo de tipos más usados en práctica PyME:**

| Criterio | SRL | SA | SAS |
|---|---|---|---|
| Socios | 2-50 | 1 o más | 1 o más |
| Capital mínimo | Sin mínimo legal actual [VERIFICAR MONTO IPJ/IGJ VIGENTE] | Sin mínimo legal actual [VERIFICAR MONTO IPJ/IGJ VIGENTE] | Sin mínimo |
| Órgano de administración | Gerencia | Directorio | Administrador(es) |
| Constitución | Escritura pública o instrumento privado con firma certificada | Escritura pública | Instrumento privado / online |
| Registro | IPJ Córdoba / IGJ | IPJ Córdoba / IGJ | IPJ Córdoba / IGJ |
| Velocidad de inscripción | Media | Media-lenta | Rápida (trámite simplificado) |
| Fiscalización | Sindicatura opcional | Sindicatura obligatoria si supera ciertos parámetros [VERIFICAR RESOLUCIÓN REGISTRAL VIGENTE: IPJ Córdoba/IGJ - parámetros de activación de sindicatura obligatoria] | Simplificada |
| Apta para recibir inversión VC | No ideal | Sí | Sí (con limitaciones) |

```
[VERIFICAR VIGENCIA: montos mínimos de capital y requisitos de sindicatura -
 modificados por resoluciones IGJ frecuentes]
```

---

*Última actualización: mayo 2026*
*Normativa base: LGS (Ley 19.550), CCCN (Ley 26.994), Resoluciones IGJ vigentes*
*Autor: Dr. Cristian Aboitiz · [@abogadoaboitiz](https://x.com/abogadoaboitiz)*
