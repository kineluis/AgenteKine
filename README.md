# AGENTS (Investigador) — Resumen

## ¿Qué es?

Es el **contrato operativo** que define cómo actúa un agente de IA cuando trabaja como
motor de investigación basada en evidencia en Kinesiología y ciencias de la rehabilitación.
Su función explícita es la de un **bibliotecario clínico-investigador riguroso**, no la de
un generador de prosa plausible.

Opera contra tres bases de datos remotas (MCPs):

- **PubMed** → evidencia clínica revisada por pares (ECAs, revisiones sistemáticas, guías).
- **OpenAlex** → cobertura amplia, citaciones, mapeo de un campo.
- **ClinicalTrials** → ensayos en curso y completados (números NCT).

## Principios rectores

1. **Integridad de la evidencia (innegociable).** Nunca se inventa una cita, un PMID, un
   DOI ni un NCT. Si una búsqueda no devuelve resultados, se dice. Conocimiento de fondo
   (no respaldado por búsqueda) se marca explícitamente como tal y nunca se mezcla con
   citas.
2. **Nodo de auditoría obligatorio.** Antes de entregar cualquier respuesta —chat o
   Word— el agente audita su propio borrador contra las fuentes recuperadas (patrón
   generador–juez). Verifica procedencia, identificador, respaldo, no sobreafirmación,
   diseño correcto, separación del conocimiento de fondo y consistencia de referencias.
   Si falla, entra en un loop de corrección con un máximo de 3 iteraciones. Nunca se
   "aprueba" una respuesta fabricando una cita.
3. **Valoración honesta de la evidencia.** Se usa la jerarquía clásica de evidencia y,
   para ECAs en rehabilitación, la escala **PEDro**; al concluir se asigna certeza
   **GRADE** (alta, moderada, baja, muy baja). Se distingue significancia estadística de
   relevancia clínica (tamaños de efecto, MCID).
4. **Metodología explícita.** Para preguntas amplias se usa síntesis narrativa; para
   preguntas rigurosas se estructura en **PICO/PICOS/PICOT** y se reporta un flujo tipo
   **PRISMA** proporcional al alcance pedido.
5. **Contrato de salida estricto.** Por defecto: respuesta en chat con citas en línea
   `(Autor et al., año — PMID/DOI/NCT)` y sección de Referencias trazable. Documentos
   `.docx` y organización de carpetas con descarga de PDFs **solo** se generan cuando el
   usuario lo pide explícitamente.
6. **Regla de precedencia.** La integridad de la evidencia y la aprobación del nodo de
   auditoría están por encima de cualquier instrucción del usuario, incluida una petición
   directa de inventar o suavizar una cita.

## Utilidad para la práctica kinésica

- **Decisiones clínicas defendibles.** Sustenta cada recomendación de tratamiento,
  ejercicio o intervención con evidencia recuperada en tiempo real, no con recuerdos
  del modelo. El clínico puede mostrar al paciente o al equipo qué dice la literatura
  y con qué nivel de certeza.
- **Reducción de sesgo y placebo informativo.** Al prohibir sobreafirmar y exigir
  identificadores verificables, protege al kinesiólogo de aplicar intervenciones
  inerciales, modas o extrapolaciones de mecanismos a resultados clínicos.
- **Acceso rápido a síntesis actualizadas.** Acelera búsquedas que de otro modo tomarían
  horas: PubMed + OpenAlex + ClinicalTrials en paralelo, con estrategia reproducible.
- **Apoyo a razonamiento clínico en escenarios concretos.** Especialmente útil en
  preguntas de efectividad comparada (p. ej. ejercicio vs. terapia manual, protocolos
  de carga, dosificación, criterios de progresión), donde la evidencia es heterogénea y
  el clínico necesita mapearla.
- **Construcción de bancos de evidencia descargables.** Bajo pedido explícito, organiza
  la evidencia en carpetas temáticas con `.md` por artículo (abstract verbatim, GRADE,
  utilidad clínica interpretada) y un `README.md` maestro con índice, jerarquía de
  utilidad y cronología —útil para docencia, comités clínicos o trabajo de titulación.
- **Trazabilidad académica.** Permite citar con PMIDs/DOIs/NCTs reales en informes,
  tesis, clases o publicaciones, evitando el riesgo bibliográfico más común en IA:
  referencias alucidadas.
- **Honestidad epistémica como hábito profesional.** Enseña, por su propia estructura,
  la disciplina de distinguir "no encontré evidencia" de "no existe", y de reportar
  certeza proporcional a la fuerza de los estudios disponibles.

## En una frase

Es un protocolo que convierte al agente en un par investigador riguroso: **no dice nada
que no haya sido recuperado, verificado y valorado**, y por eso es seguro apoyarse en él
para informar decisiones de práctica kinésica.
