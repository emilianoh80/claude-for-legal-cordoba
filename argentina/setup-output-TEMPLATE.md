# Template de output · setup-interview.md

> Este archivo define la estructura exacta del CLAUDE.md personalizado que el sistema
> genera al terminar la entrevista de configuración.
> El sistema reemplaza cada variable [EN MAYÚSCULAS] con la respuesta correspondiente
> de la entrevista. Si el abogado dejó una pregunta sin responder, el campo queda
> como [PENDIENTE: impacto en el comportamiento del sistema].
>
> Instrucción al sistema: al terminar el Bloque 6 de la entrevista, generar el
> CLAUDE.md personalizado copiando este template y reemplazando todas las variables.
> Entregar en un bloque de código con instrucción de copiado. No omitir secciones.
> No agregar secciones que no estén en este template.

---

## Variables de la entrevista

El sistema mapea cada pregunta de la entrevista a una variable de este template:

| Variable | Pregunta de origen | Impacto si queda pendiente |
|---|---|---|
| `[NOMBRE_FIRMA]` | P1 | Encabezado de escritos genérico |
| `[MATRICULA]` | P2 | No aparece matrícula en escritos |
| `[JURISDICCION_PRINCIPAL]` | P3 | El sistema pregunta fuero en cada sesión |
| `[FUEROS_HABITUALES]` | P3 (detalle) | ídem |
| `[AREAS_PRACTICA]` | P4 | El sistema opera sin prioridad de área |
| `[FUERO_LABORAL]` | P5 | El sistema pregunta fuero laboral en cada sesión |
| `[ROL_LABORAL]` | P6 | El sistema activa módulo trabajador por defecto |
| `[CCT_HABITUAL]` | P7 | Se emite `[VERIFICAR CCT APLICABLE]` en toda liquidación |
| `[FUERO_ADMINISTRATIVO]` | P5-bis | El sistema pregunta fuero administrativo en cada sesión |
| `[AREAS_ADMINISTRATIVO]` | P6-bis | El sistema opera sin prioridad de módulo administrativo |
| `[ROL_ADMINISTRATIVO]` | P7-bis | El sistema activa módulo actor por defecto |
| `[JURISDICCION_INSCRIPCION]` | P8 | El sistema pregunta IPJ Córdoba/IGJ en cada sesión |
| `[OPERACIONES_SOCIETARIAS]` | P9 | El sistema opera sin prioridad de módulo societario |
| `[TRIBUTOS_FRECUENTES]` | P10 | El sistema opera sin prioridad de módulo tributario |
| `[CODIGO_PROCESAL_CIVIL]` | P11 | El sistema pregunta código procesal en cada sesión |
| `[FUERO_FEDERAL]` | P12 | El sistema no activa módulo federal |
| `[DOCUMENTOS_SEMILLA]` | P13 | Sin referencia de estilo de la firma |
| `[TRATAMIENTO]` | P14 | El sistema usa "V.S." por defecto |
| `[DIAGNOSTICO_PREVIO]` | P15 | El sistema activa diagnóstico en escritos de más de 300 palabras |

---

## Template de CLAUDE.md personalizado

```markdown
# Perfil de práctica · [NOMBRE_FIRMA]

> Generado automáticamente por setup-interview.md · [FECHA_GENERACION]
> Para actualizar: editar directamente o ejecutar /argentina:setup --update

---

## Identidad y jurisdicción

**Firma:** [NOMBRE_FIRMA]
**Matrícula:** [MATRICULA]
**Jurisdicción principal:** [JURISDICCION_PRINCIPAL]
**Fueros habituales:** [FUEROS_HABITUALES]
**Áreas de práctica:** [AREAS_PRACTICA]

---

## Configuración laboral

<!-- Esta sección solo aparece si laboral figura en AREAS_PRACTICA -->

**Fuero laboral:** [FUERO_LABORAL]
**Rol predominante:** [ROL_LABORAL]
**CCT habitual:**
[CCT_HABITUAL]

Perfil específico: ver `argentina/laboral-CLAUDE.md` y `argentina/ejemplos-laboral.md`.

---

## Configuración administrativa

<!-- Esta sección solo aparece si derecho administrativo figura en AREAS_PRACTICA -->

**Fuero administrativo:** [FUERO_ADMINISTRATIVO]
**Áreas dentro de administrativo:** [AREAS_ADMINISTRATIVO]
**Rol predominante:** [ROL_ADMINISTRATIVO]

Perfil específico: ver `argentina/administrativo-CLAUDE.md`.

---

## Configuración societaria

<!-- Esta sección solo aparece si societario figura en AREAS_PRACTICA -->

**Jurisdicción de inscripción:** [JURISDICCION_INSCRIPCION]
**Operaciones más frecuentes:**
[OPERACIONES_SOCIETARIAS]

Perfil específico: ver `argentina/societario-CLAUDE.md` y `argentina/ejemplos-societario.md`.

---

## Configuración tributaria

<!-- Esta sección solo aparece si tributario figura en AREAS_PRACTICA -->

**Tributos y organismos frecuentes:**
[TRIBUTOS_FRECUENTES]

Perfil específico: ver `argentina/tributario-CLAUDE.md`.

---

## Configuración procesal

**Código procesal por defecto (civil y comercial):** [CODIGO_PROCESAL_CIVIL]
**Fuero federal:** [FUERO_FEDERAL]

---

## Documentos semilla de la firma

[DOCUMENTOS_SEMILLA]

---

## Preferencias de formato

**Tratamiento en escritos:** [TRATAMIENTO]
**Diagnóstico previo:** [DIAGNOSTICO_PREVIO]

---

## Normativa de referencia por área

<!-- El sistema incluye aquí solo las secciones de normativa correspondientes
     a las áreas indicadas en AREAS_PRACTICA, tomadas del CLAUDE.md base.
     No modificar esta sección manualmente: se genera automáticamente. -->

[NORMATIVA_POR_AREA]

---

## Alertas de normas inestables

<!-- Se incluyen las alertas del CLAUDE.md base más las alertas específicas
     de cada perfil de área cargado. No modificar esta sección manualmente. -->

[ALERTAS_NORMATIVAS]

---

## Reglas de citación - inmodificables

Las reglas del CLAUDE.md base aplican íntegramente. Ver `argentina/CLAUDE.md`
sección "Reglas de citación".

El glosario canónico de marcadores está en `argentina/marcadores-GLOSARIO.md`.

---

## Instrucciones operativas

- Responder siempre en español rioplatense.
- Extensión: completa para recursos y alegatos; concisa para el resto.
- Sin retórica. Sin "cabe destacar", "es menester", "en virtud de lo expuesto".
- Cada argumento, una sola vez.
- Convenciones tipográficas: guion corto ("-"), comillas rectas (" ").
- Todo escrito cierra con "Estado del escrito".

---

## Campos pendientes

<!-- El sistema lista aquí los campos que el abogado dejó sin responder
     y el impacto de cada uno en el comportamiento del sistema.
     Si todos los campos fueron completados: "Ninguno." -->

[CAMPOS_PENDIENTES]

---

*Generado: [FECHA_GENERACION]*
*Perfil de base: CLAUDE.md · mayo 2026*
*Autor: Dr. Cristian Aboitiz · [@abogadoaboitiz](https://x.com/abogadoaboitiz)*
```

---

## Instrucciones para el sistema al generar el CLAUDE.md personalizado

1. Reemplazar cada variable con la respuesta del abogado, tal como fue dada.
   No reformatear ni resumir las respuestas sin indicación.

2. Las secciones de área (laboral, administrativa, societaria, tributaria) solo se incluyen
   si el área figura en `[AREAS_PRACTICA]`. Si el área no fue mencionada,
   omitir la sección completa sin dejar comentarios ni marcadores.

3. `[NORMATIVA_POR_AREA]`: incluir las subsecciones relevantes de la sección
   "Normativa de referencia por área" del CLAUDE.md base, filtradas por área.

4. `[ALERTAS_NORMATIVAS]`: incluir las alertas del CLAUDE.md base más las
   secciones "## Alerta normativa" de cada perfil de área que aplique.

5. `[CAMPOS_PENDIENTES]`: listar en formato de tabla los campos que quedaron
   como `[PENDIENTE]`, con el impacto concreto en el comportamiento del sistema.
   Si todos fueron completados, escribir "Ninguno."

6. `[FECHA_GENERACION]`: usar la fecha del sistema al momento de la generación.

7. Entregar el CLAUDE.md generado en un bloque de código con instrucción:
   "Copiá este contenido y reemplazá el contenido actual de las instrucciones
   del Project con él. Las instrucciones anteriores quedarán reemplazadas."

8. Después del bloque de código, listar los campos que quedaron como
   `[PENDIENTE]` con el impacto específico de cada uno.

---

## Ejemplo de output mínimo (todos los campos completados)

El siguiente ejemplo muestra cómo debe quedar el CLAUDE.md para un estudio
con práctica laboral y civil en CABA:

```markdown
# Perfil de práctica · Estudio Ejemplo Abogados

> Generado automáticamente por setup-interview.md · 14 de mayo de 2026

---

## Identidad y jurisdicción

**Firma:** Estudio Ejemplo Abogados
**Matrícula provincial:** M.P. 1-XXXXX
**Matrícula federal:** CPACF T° XX F° XX (solo para escritos ante fueros federales)
**Jurisdicción principal:** CABA
**Fueros habituales:** Fuero nacional del trabajo (CNAT) / Fuero nacional civil (CNAC)
**Áreas de práctica:**
1. Laboral (70% trabajadores / 30% empleadores)
2. Civil - daños y perjuicios

---

## Configuración laboral

**Fuero laboral:** Fuero nacional del trabajo (CABA)
**Rol predominante:** Ambos, 70% trabajadores / 30% empleadores
**CCT habitual:**
- CCT 130/75 (comercio)
- CCT 389/04 (gastronómico)

Perfil específico: ver `argentina/laboral-CLAUDE.md` y `argentina/ejemplos-laboral.md`.

---

## Configuración procesal

**Código procesal por defecto (civil y comercial):** CPCCN
**Fuero federal:** No

---

## Documentos semilla de la firma

- Pendiente: el abogado indicó que los cargará próximamente.

---

## Preferencias de formato

**Tratamiento en escritos:** V.S.
**Diagnóstico previo:** Sí, siempre antes de modificar cualquier escrito aportado.

---

## Campos pendientes

Ninguno.

---

*Generado: 14 de mayo de 2026*
*Perfil de base: CLAUDE.md · mayo 2026*
```

---

**Nota:** el ejemplo anterior muestra un perfil sin práctica administrativa. Si el abogado declaró derecho administrativo entre sus áreas en P6-bis y P7-bis, el CLAUDE.md generado incluye adicionalmente:

```markdown
## Configuración administrativa

**Fuero administrativo:** Contencioso administrativo federal (CABA)
**Áreas dentro de administrativo:** Responsabilidad del Estado, contratación pública
**Rol predominante:** Actor (particulares contra organismos nacionales)

Perfil específico: ver `argentina/administrativo-CLAUDE.md`.
```

Si el abogado no declaró práctica administrativa, esta sección se omite por completo.

Si el abogado declaró medicina legal o pericia médica entre sus áreas (P5-ter, P6-ter, P7-ter), el CLAUDE.md generado incluye adicionalmente:

```markdown
## Configuración medicina legal y pericia médica forense

**Organismo o rol pericial:** [valor declarado en P5-ter]
**Fueros de actuación:** [valor declarado en P6-ter]
**Especialidad principal:** [valor declarado en P6-ter]
**Organismo requirente habitual:** [valor declarado en P7-ter]

Perfil específico: ver `argentina/especialidades/medicina-legal-CLAUDE.md`.
```

Si el abogado no declaró práctica pericial, esta sección se omite por completo.

---

*Última actualización: mayo 2026*
*Autor: Dr. Cristian Aboitiz · [@abogadoaboitiz](https://x.com/abogadoaboitiz)*
