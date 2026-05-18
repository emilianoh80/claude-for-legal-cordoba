# Estado del fork · claude-for-legal-cordoba

Repo: https://github.com/emilianoh80/claude-for-legal-cordoba
Basado en: https://github.com/cristianaboitiz-eng/claude-for-legal-argentina (Dr. Cristian Aboitiz)
Directorio local: `/Users/emilianoherrera/claudelegal/claude-for-legal-cordoba/`

---

## Qué es este repo

Adaptación de claude-for-legal para práctica jurídica en la **Provincia de Córdoba**.
Reemplaza todo el contenido específico de PBA/CABA por equivalentes cordobeses.
La normativa nacional (CCCN, LCT, LGS, etc.) y la arquitectura del sistema se mantienen intactas.

---

## Cambios aplicados

### Reemplazos sistemáticos completados

| Elemento original (PBA) | Reemplazado por (Córdoba) |
|---|---|
| SCBA / scba.gov.ar | TSJ Córdoba / jurisprudencia.justiciacordoba.gob.ar |
| CPCCBA (Ley 7425) | CPCC Córdoba (Ley 8465) |
| Ley 11.653 (proceso laboral PBA) | Ley 7987 (CPT Córdoba) |
| Decreto-Ley 7647/70 + Ley 12.008 | Ley 5350/6658 + Ley 7182 |
| DPPJ / IGPJ | IPJ Córdoba (Inspección de Personas Jurídicas de Córdoba) |
| AGIP / ARBA (ingresos brutos) | DGR / ARCO Córdoba |
| Ley 12.569 (violencia familiar PBA) | Ley 9.283 Córdoba |
| CPPBA (Ley 11.922) | CPP Córdoba (Ley 8123) |
| Departamentos judiciales PBA | Circunscripciones 1ª–10ª de Córdoba |
| Mediación PBA (Ley 13.951) | Mediación Córdoba (Ley 8858) |

### Archivos modificados (17 en commit principal + correcciones posteriores)

- `CLAUDE.md` (raíz) — sincronizado con argentina/CLAUDE.md
- `argentina/CLAUDE.md` — secciones de fueros, procesal, societario, administrativo
- `argentina/laboral-CLAUDE.md` — fuero laboral Córdoba, Ley 7987, sin SECLO
- `argentina/administrativo-CLAUDE.md` — Ley 7182, Ley 5350/6658, TSJ Sala CA
- `argentina/civil-CLAUDE.md` — CPCC Cba, Ley 8858 (mediación), TSJ Sala Civil
- `argentina/societario-CLAUDE.md` — IPJ Córdoba
- `argentina/tributario-CLAUDE.md` — DGR/ARCO, Código Tributario Córdoba (Ley 6006)
- `argentina/penal-CLAUDE.md` — CPP Córdoba (Ley 8123), TSJ Sala Penal
- `argentina/familia-CLAUDE.md` — Ley 9.283, Ley 8858, TSJ Sala Civil
- `argentina/concursos-CLAUDE.md` — CPCC Córdoba, TSJ Sala Civil
- `argentina/setup-interview.md` — opciones de fuero, matrícula CAC, circunscripciones
- `argentina/fuentes.md` — TSJ Córdoba, IPJ, DGR, tabla de conectores
- `argentina/marcadores-GLOSARIO.md` — TSJ Córdoba, IPJ
- `argentina/ejemplos-civil.md` — tabla de fórmulas de daños por fuero
- `argentina/ejemplos-societario.md` — IPJ, DGR Córdoba
- `argentina/diagnostico-casos-prueba.md` — IPJ
- `argentina/setup-output-TEMPLATE.md` — IPJ
- `README.md` — descripción, normativa base, autor del fork

### Correcciones posteriores
- URL del TSJ: `tsj.jus.cba.gov.ar` (inexistente) → `jurisprudencia.justiciacordoba.gob.ar`
- Nombre organismo societario: IGPJ → IPJ (Inspección de Personas Jurídicas de Córdoba)
- Root `CLAUDE.md` no había sido actualizado en el primer commit — corregido

---

## Pendiente de verificación (datos locales a confirmar)

Estos datos los puse con `[VERIFICAR VIGENCIA]` pero conviene confirmarlos con alguien que practique en Córdoba:

| Archivo | Dato a confirmar | Estado |
|---|---|---|
| `laboral-CLAUDE.md` | ¿Hay conciliación previa obligatoria ante MTSS antes de ir a Cámaras del Trabajo? ¿O se demanda directo? | ❓ |
| `laboral-CLAUDE.md` | ¿La alzada del fuero laboral es directo al TSJ - Sala Laboral, o hay cámara intermedia? | ❓ |
| `penal-CLAUDE.md` | ¿CPP Córdoba es Ley 8123 vigente, o hubo reforma posterior con nueva numeración? | ❓ |
| `penal-CLAUDE.md` | ¿Los órganos se llaman "Cámara de Acusación" y "Cámara en lo Criminal"? | ❓ |
| `familia-CLAUDE.md` | ¿Ley 9.283 es la ley de violencia familiar vigente en Córdoba? | ❓ |
| `civil-CLAUDE.md` | ¿Ley 8858 es la ley de mediación prejudicial vigente en Córdoba? | ❓ |
| `tributario-CLAUDE.md` | ¿El organismo recaudador se llama DGR, ARCO, u otro nombre? ¿URL correcta? | ❓ |
| `administrativo-CLAUDE.md` | ¿Ley 5350 t.o. Ley 6658 es la denominación correcta de la LPA Córdoba? | ❓ |

---

## Cómo usar el repo

### Opción A — Claude.ai Projects (sin instalar nada)

1. Crear un Project nuevo en claude.ai
2. Copiar el contenido de `argentina/CLAUDE.md` en las instrucciones del sistema
3. En el chat escribir: **"Corré la entrevista de configuración"**
4. Responder las ~15 preguntas (firma, matrícula CAC, circunscripción, áreas)
5. El sistema genera un CLAUDE.md personalizado → reemplazar las instrucciones con ese
6. Para cada área de práctica, agregar el perfil correspondiente a las instrucciones:
   - Laboral → `laboral-CLAUDE.md` + `ejemplos-laboral.md`
   - Civil → `civil-CLAUDE.md` + `ejemplos-civil.md`
   - Societario → `societario-CLAUDE.md` + `ejemplos-societario.md`
   - Administrativo → `administrativo-CLAUDE.md`
   - Tributario → `tributario-CLAUDE.md`
   - Penal → `penal-CLAUDE.md`
   - Familia → `familia-CLAUDE.md`
   - Contratos → `contratos-CLAUDE.md` + `red-flags-contratos.md`
   - Concursos → `concursos-CLAUDE.md`

### Opción B — Claude Code / Cowork

Instalar como plugin y ejecutar `/argentina:setup` en la terminal.

---

## Próximos pasos sugeridos

1. Confirmar los datos locales de la tabla de pendientes
2. Probar con consultas reales de cada área para detectar errores de contenido
3. Agregar jurisprudencia del TSJ Córdoba relevante en los perfiles de área
4. Considerar agregar ejemplos locales (ej: liquidaciones con CCTs cordobeses frecuentes)

---

*Última actualización: mayo 2026*
