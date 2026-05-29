# legal.local.md · Configuración local del estudio

> Este archivo es tuyo. No lo subas al repositorio ni lo compartas.
> Contiene datos del estudio que el sistema usa como contexto por defecto,
> sin que tengas que repetirlos en cada sesión.
>
> Instrucciones: copiá este archivo como `legal.local.md` en el mismo
> directorio donde tenés tu `CLAUDE.md`. Completá las secciones que usás
> y dejá en blanco o borrá las que no aplican.
>
> El sistema lee este archivo cuando está disponible. Si una variable está
> vacía, el sistema pregunta o usa el valor genérico del perfil de área.

---

## Estudio

```
NOMBRE_ESTUDIO:
MATRICULA_TITULAR:        # CPACF / colegio provincial
COLEGIO:                  # CPACF | CALZ | CAMdP | CAR | otro
DOMICILIO_CONSTITUIDO:
CUIT_ESTUDIO:
SISTEMA_GESTION:          # Lexis | Estudio | Aqua | Manual | otro
SISTEMA_PRESENTACION:     # Lex100 | Augusta | MEJ | SCBA online | otro
```

---

## Práctica general

```
JURISDICCION_HABITUAL:    # CABA | PBA | Federal | mixta
FUERO_HABITUAL:           # Civil | Comercial | Laboral | Penal | Contencioso | Familia | otro
DEPARTAMENTO_JUDICIAL:    # (solo PBA) Morón | San Isidro | La Plata | Lomas | Mar del Plata | otro
```

---

## Civil y comercial

```
FUERO_CIVIL:              # Nacional Civil | Nacional Comercial | Civil y Comercial PBA | otro
DEPARTAMENTO_CIVIL:       # (PBA) departamento judicial habitual
TASA_INTERES_HABITUAL:    # tasa activa BNA | tasa pasiva BCRA | tasa mix | según fuero
FORMULA_DANOS:            # Méndez | Vuoto | otra | según fuero
NOTIFICACION_HABITUAL:    # cédula papel | cédula electrónica (NEF) | domicilio electrónico
```

---

## Laboral

```
FUERO_LABORAL:            # CNAT | Tribunal del Trabajo PBA | Juzgado de Paz | otro
SALA_HABITUAL_CNAT:       # A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | sin preferencia
DEPARTAMENTO_LABORAL:     # (PBA) departamento judicial habitual
CCT_HABITUAL:             # número y actividad del CCT que más usás
TASA_LABORAL:             # tasa activa BNA | tasa CNAT | según sala
INDEMNIZACION_TOPE:       # actualizar con el tope vigente art. 245 LCT al momento de uso
```

---

## Penal

```
FUERO_PENAL:              # Nacional Criminal y Correccional | Federal | CABA | PBA | otro
CODIGO_PROCESAL:          # CPPN (Ley 23.984) | CPPF (Ley 27.063) | CPPCABA | CPPBA | otro
DEPARTAMENTO_PENAL:       # (PBA) departamento judicial habitual
ROL_HABITUAL:             # defensa | querella | ambos
ETAPA_HABITUAL:           # instrucción | juicio oral | casación | todas
FLAGRANCIA:               # sí | no  (si usás el proceso de flagrancia Ley 27.272)
```

---

## Familia

```
FUERO_FAMILIA:            # Nacional Civil (juzgados de familia) | Tribunal de Familia PBA | Juzgado de Paz | otro
DEPARTAMENTO_FAMILIA:     # (PBA) departamento judicial habitual
REGIMEN_PATRIMONIAL:      # comunidad | separación | ambos  (régimen que más trabajás)
CUOTA_ALIMENTARIA_REF:    # porcentaje o monto de referencia habitual para alimentos
```

---

## Administrativo

```
FUERO_ADMINISTRATIVO:     # CNACAF | CAyT CABA | Contencioso Administrativo PBA | Federal otro | mixto
CAMARA_HABITUAL:          # (CNACAF) Sala I | II | III | IV | V | sin preferencia
ORGANISMO_HABITUAL:       # AFIP/ARCA | ANSES | ministerio | ente regulador | otro
VIA_AGOTAMIENTO:          # LNPA (Ley 19.549) | LPACBA (Ley 6.017) | CPCA PBA | otro
PLAZO_CADUCIDAD_REF:      # art. 25 LNPA (90 días hábiles) | plazo especial aplicable
```

---

## Tributario

```
FUERO_TRIBUTARIO:         # TFN | CNACAF | CABA | PBA | mixto
IMPUESTO_HABITUAL:        # Ganancias | IVA | Bienes Personales | Ingresos Brutos | todos
ORGANISMO_FISCAL:         # AFIP/ARCA | AGIP | ARBA | otro
REGIMEN_SIMPLIFICADO:     # sí | no  (si trabajás monotributo regularmente)
```

---

## Societario y M&A

```
REGISTRO_HABITUAL:        # IGJ | DPPJ | otro registro provincial
TIPO_SOCIETARIO_HABITUAL: # SA | SRL | SAS | mixto
OPERACIONES_HABITUALES:   # constitución | M&A | due diligence | pactos | todas
CNDC:                     # sí | no  (si trabajás concentraciones económicas)
```

---

## Concursal

```
FUERO_CONCURSAL:          # Nacional Comercial | Comercial PBA | otro
DEPARTAMENTO_CONCURSAL:   # (PBA) departamento judicial habitual
ROL_HABITUAL_CONCURSAL:   # concursado | acreedor | síndico | otro
PERIODO_SOSPECHA_REF:     # fecha de cesación de pagos habitual en los casos que trabajás
```

---

## Contratos

```
LEY_APLICABLE_HABITUAL:   # CCCN | LDC | LCT | LGS | mixto
TIPO_CONTRATO_HABITUAL:   # NDA | servicios | compraventa | locación | todos
PARTE_HABITUAL:           # redactor | revisor | ambos
REGIMEN_CAMBIARIO_NOTA:   # actualizar con restricciones BCRA vigentes al momento de uso
```

---

## Privacidad y datos personales

```
REGIMEN_APLICABLE:        # Ley 25.326 | proyecto de reforma | ambos
AUTORIDAD_APLICACION:     # AAIP
SECTOR_HABITUAL:          # salud | financiero | tecnología | general
TRANSFERENCIA_INTERNACIONAL: # sí | no  (si trabajás transferencias internacionales de datos)
```

---

## Preferencias de formato y entrega

```
FORMATO_CARATULA:         # modelo de carátula habitual (texto libre o referencia a template)
FORMATO_FIRMA:            # texto libre con datos de firma para escritos
ESTILO_CITAS:             # inline | nota al pie | sin preferencia
IDIOMA_MARCADORES:        # español | inglés | según perfil
LONGITUD_PREFERIDA:       # concisa | estándar | extensa
```

---

## Notas libres

> Cualquier instrucción adicional que no encaje en las secciones anteriores.
> Criterios dogmáticos de preferencia, doctrina de valoración de prueba digital,
> jueces o salas con criterios conocidos, particularidades del estudio.

```
NOTAS:
```

---

*No subir este archivo al repositorio. Agregarlo a `.gitignore`.*
