# Setup interview · claude-for-legal Argentina

> Entrevista de configuración inicial. Responder una sola vez por estudio o abogado.
> El sistema usa las respuestas para generar el CLAUDE.md personalizado que se carga
> en las instrucciones del Project (Claude.ai) o en el perfil del plugin (Claude Code / Cowork).
>
> Tiempo estimado: 10 minutos.
> Las respuestas quedan guardadas en tu CLAUDE.md. Podés editarlas en cualquier momento
> o volver a correr la entrevista para regenerarlas.

---

## Cómo usar este archivo

**En Claude.ai (Projects):**
1. Crear un nuevo Project.
2. Pegar el contenido de este archivo en las instrucciones del sistema.
3. En el chat, escribir: "Corré la entrevista de configuración".
4. Responder las preguntas. Al terminar, pedirle al sistema que genere tu CLAUDE.md personalizado.
5. Reemplazar el contenido de las instrucciones del sistema con el CLAUDE.md generado.

**En Claude Code / Cowork:**
1. Instalar el plugin según las instrucciones del README.
2. Ejecutar `/argentina:setup` en la terminal.
3. Responder las preguntas. El sistema escribe el CLAUDE.md en
   `~/.claude/plugins/config/claude-for-legal/argentina/CLAUDE.md`.

---

## Preguntas de la entrevista

El sistema hace estas preguntas en secuencia. Para cada una hay un ejemplo de respuesta
y una nota sobre el impacto en el comportamiento del sistema.

---

### Bloque 1 - Identidad profesional

**P1. Nombre del estudio o profesional**

Ejemplo: `Estudio Aboitiz Abogados` / `Dr. Juan Pérez, abogado`

Impacto: aparece en el encabezado de escritos y en el cierre de informes.

---

**P2. Matrícula y colegio**

Ejemplo: `CAC T° XX F° XX` (Colegio de Abogados de Córdoba) / `CPACF T° XX F° XX` (si actuás en fueros nacionales)

Impacto: el sistema incluye la matrícula en escritos donde corresponde. Si no querés que
aparezca en los borradores, indicá "no incluir en escritos".

---

**P3. Jurisdicción principal**

Indicar la jurisdicción donde tramitan la mayoría de las causas.

Opciones orientativas:
- Córdoba - indicar circunscripción judicial (1ª a 10ª; 1ª = Ciudad de Córdoba)
- CABA (fueros nacionales)
- Multijurisdiccional

Impacto: determina el código procesal que el sistema aplica por defecto sin preguntar
en cada sesión. Si trabajás en más de una jurisdicción, indicá el orden de prioridad.

---

**P4. Áreas de práctica**

Listar las áreas en orden de volumen de trabajo, de mayor a menor.

Ejemplo:
```
1. Laboral (trabajadores y empleadores)
2. Civil - daños y perjuicios
3. Societario
```

Impacto: el sistema carga los perfiles de área correspondientes con mayor prioridad
y sugiere los módulos relevantes en cada consulta.

---

### Bloque 2 - Configuración laboral

Responder solo si laboral figura entre las áreas de práctica.

---

**P5. Fuero laboral habitual**

Opciones: fuero laboral Córdoba - [circunscripción] / fuero nacional del trabajo (CABA) / ambos / otro.

Impacto: el sistema aplica el código procesal correcto (Ley 7987 para Córdoba / Ley 18.345 para fuero nacional)
y verifica el SECLO solo cuando corresponde al fuero nacional. En Córdoba el SECLO no aplica.

---

**P6. Rol predominante en causas laborales**

Opciones: trabajador / empleador / ambos (indicar proporción aproximada si la sabés).

Ejemplo: `Ambos, 70% trabajadores / 30% empleadores`

Impacto: el sistema activa el módulo de análisis estratégico correspondiente por defecto.
En cada sesión podés cambiarlo con una instrucción explícita.

---

**P7. CCTs más frecuentes**

Listar los convenios colectivos que aparecen con mayor frecuencia, con número si lo tenés.

Ejemplo:
```
- CCT 130/75 (comercio)
- CCT 389/04 (gastronómico)
- CCT 40/89 (construcción - UOCRA)
```

Si trabajás con múltiples CCTs sin uno predominante: `Variable - verificar en cada caso`.

Impacto: sin este dato, el sistema emite el marcador `[VERIFICAR CCT APLICABLE]`
en toda liquidación. Con los CCTs cargados, solo lo emite cuando el caso se sale de la lista.

---

### Bloque 2-bis - Configuración administrativa

Responder solo si derecho administrativo figura entre las áreas de práctica.

---

**P5-bis. Fuero administrativo habitual**

Opciones: contencioso administrativo Córdoba (Ley 7182) / contencioso administrativo federal (CABA) / combinación de los anteriores.

Impacto: el sistema aplica el código y los plazos del fuero indicado sin preguntar en cada sesión. El plazo de caducidad para accionar varía entre fueros (90 días hábiles judiciales en el federal; verificar Ley 7182 para Córdoba). Sin este dato, el sistema pregunta el fuero en cada consulta administrativa.

---

**P6-bis. Áreas dentro de administrativo**

Listar las áreas de mayor volumen dentro de la práctica administrativa, de mayor a menor.

Ejemplo:
```
1. Responsabilidad del Estado
2. Empleo público nacional
3. Contratación pública (obra pública)
```

Si la práctica administrativa es ocasional o de área única: indicarlo.

Impacto: el sistema prioriza la lógica de análisis correspondiente (vicios del acto, agotamiento de la vía, instancias recursivas, régimen de responsabilidad, sumario administrativo, etc.) según las áreas declaradas.

---

**P7-bis. Rol predominante en causas administrativas**

Opciones: actor (particular contra el Estado) / demandado (Estado o ente en defensa) / ambos (indicar proporción aproximada).

Ejemplo: `Predominantemente actor, 80% particulares contra organismos nacionales`

Impacto: el sistema activa el módulo de análisis estratégico correspondiente por defecto. En causas como actor: prioriza agotamiento de la vía, plazos de caducidad y requisitos de admisibilidad. En causas como demandado: prioriza análisis de vicios del acto, defensa de la regularidad del procedimiento y legitimidad del accionar estatal.

---

### Bloque 3 - Configuración societaria

Opciones: IGPJ Córdoba / IGJ (CABA) / ambas / otra provincia.

Impacto: el sistema aplica la normativa registral correcta en due diligence y constitución
de sociedades.

---

**P9. Tipo de operaciones societarias más frecuentes**

Ejemplo:
```
- Constitución de SAS y SRL para clientes PyME
- Due diligence en operaciones de compraventa de empresas medianas
- Pactos de accionistas
```

Impacto: el sistema prioriza los módulos de análisis correspondientes.

---

### Bloque 4 - Configuración tributaria

Responder solo si tributario figura entre las áreas de práctica.

---

**P10. Tributos y organismos más frecuentes**

Ejemplo:
```
- IVA y Ganancias ante AFIP
- Ingresos brutos Córdoba (DGR / ARCO)
- Litigio ante el TFN
```

Impacto: el sistema activa los módulos de verificación correspondientes y aplica
los plazos del fuero correcto.

---

### Bloque 5 - Configuración procesal general

---

**P11. Código procesal por defecto para causas civiles y comerciales**

Opciones: CPCC Córdoba (Ley 8465) / CPCCN (fueros nacionales) / ambos (indicar cuál es principal).

Impacto: el sistema no equipara automáticamente plazos e institutos entre códigos.
Este dato evita preguntas repetitivas sobre el fuero en cada sesión.

---

**P12. ¿Actuás en fuero federal (contencioso administrativo federal, penal federal)?**

Sí / No / Ocasionalmente.

Impacto: si la respuesta es sí u ocasionalmente, el sistema activa el módulo federal
y verifica agotamiento de vía administrativa antes de analizar acciones judiciales.

---

### Bloque 6 - Estilo y documentos de referencia

---

**P13. Documentos semilla de la firma**

Listar los documentos que el sistema usará como referencia de estilo y criterio.
Estos son los más importantes para la calidad del output: el sistema aprende
el estilo de redacción de la firma leyendo estos modelos.

Ejemplos:
```
- Contrato de prestación de servicios profesionales estándar de la firma
- Modelo de NDA usado habitualmente
- Sentencia o resolución favorable representativa
- Escrito de demanda laboral tipo
```

Para cargarlos: adjuntarlos como archivos en el Project (Claude.ai) o incluirlos
en la carpeta `argentina/semilla/` del repo (Claude Code).

Si no tenés documentos para cargar ahora: indicá `Pendiente` y completarlo después.
El sistema funciona sin documentos semilla, pero la calidad de estilo mejora con ellos.

---

**P14. Preferencias de formato en escritos**

Indicar si tenés preferencias sobre:
- Tratamiento ("V.S." / "V.E." / "Su Señoría")
- Encabezado habitual
- Estructura de petitorio
- Cualquier convención interna de la firma

Si no tenés preferencias específicas: `Seguir convenciones estándar del fuero`.

---

**P15. ¿Querés que el sistema haga diagnóstico previo antes de modificar cualquier escrito aportado?**

Opciones: Sí, siempre / Solo en escritos de más de 500 palabras / No por defecto (activar por instrucción).

Impacto: cuando está activado, antes de modificar cualquier escrito el sistema entrega
un bloque de diagnóstico con argumentos sin norma de respaldo, hechos no acreditados,
citas no verificadas y contradicciones internas. Luego espera instrucción antes de proceder.

---

## Output de la entrevista

Al terminar de responder, el sistema genera un CLAUDE.md personalizado con:

1. Identidad y jurisdicción completadas con tus datos.
2. Normativa de referencia priorizada por tus áreas de práctica.
3. Configuración laboral (si aplica): fuero, rol y CCTs cargados.
4. Configuración administrativa (si aplica): fuero, áreas y rol (actor/demandado) cargados.
5. Configuración societaria (si aplica): jurisdicción de inscripción y módulos activados.
6. Configuración tributaria (si aplica): tributos y fuero de litigio.
7. Documentos semilla referenciados (si los cargaste).
8. Preferencias de formato registradas.
9. Regla de diagnóstico previo configurada según tu respuesta.

El archivo generado reemplaza el CLAUDE.md genérico del repo. Podés editarlo
directamente o volver a correr la entrevista para regenerarlo.

---

## Actualización del perfil

El perfil no es estático. Actualizarlo cuando:

- Cambia la jurisdicción principal o se agrega un fuero nuevo.
- Se incorpora un área de práctica nueva.
- Cambia el CCT predominante en la cartera.
- Se agregan documentos semilla nuevos.
- Hay un cambio normativo relevante que afecta el perfil (el sistema también puede
  sugerir actualizaciones cuando detecta normas modificadas).

Para actualizar: editar el CLAUDE.md directamente, o correr `/argentina:setup --update`
en Claude Code para hacer solo las preguntas cuyas respuestas cambiaron.

---

*Última actualización: mayo 2026*
*Fork Córdoba — basado en el trabajo de Dr. Cristian Aboitiz · [@abogadoaboitiz](https://x.com/abogadoaboitiz)*
