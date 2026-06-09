# Raw Conversation Notes Consolidated

> Generated for NotebookLM from `.raw`. This is a full-content consolidation, not a summary.

## Source Files

- `.raw/00-chat.md`
- `.raw/01-chat.md`
- `.raw/02-chat.md`
- `.raw/03-chat.md`
- `.raw/04-chat.md`
- `.raw/05-chat.md`
- `.raw/06-chat.md`
- `.raw/07-chat.md`
- `.raw/08-chat.md`
- `.raw/09-chat.md`
- `.raw/README.md`

## Consolidated Content


---

## Source: `.raw/00-chat.md`

# Lectura Estratégica De La Hackathon

> Nota raw formateada desde la primera conversación estratégica.

> Decisión posterior: este archivo conserva la exploración original. El nombre final de trabajo para el proyecto es **GradeOps AI**; **ClassOps AI** queda como alternativa histórica de naming, no como marca principal.

## Contexto Inicial

Voy a revisar las bases públicas de la hackathon, extraer criterios, restricciones, entregables y señales de evaluación. Con eso te propongo una idea vendible, no solo "interesante técnicamente", y la bajo a pitch, MVP y estrategia de demo.

Ya hay una señal crítica: no es una hackathon clásica de "demo bonita". La evaluación está diseñada como una mini startup: negocio real, usuarios reales, ingresos reales, operación con agentes y evidencia verificable.

## Tesis Principal

Esta hackathon no premia "la mejor app con IA". Premia el negocio real más convincente operado por IA.

La página lo deja bastante claro: el reto pide construir un negocio en 90 días, con clientes reales, ingresos reales, operación con IA y uso de al menos un producto de Google Cloud. Además, si el proyecto usa LLM, debe usar Gemini API en al menos una llamada del producto desplegado.

La fecha límite es **17 de agosto de 2026 a las 13:00 PDT**, y hoy, **8 de junio de 2026**, quedan aproximadamente **70 días**. La competencia ya muestra alrededor de **11.6k participantes**, por lo que no conviene competir con una idea genérica tipo "chatbot educativo", "copilot de finanzas" o "asistente para pymes".

Los criterios pesan igual, pero el desempate favorece primero **Business Viability**, luego **AI-Native Operations** y luego **Category Impact**. Eso significa que vender puede pesar más que tener la arquitectura más elegante.

## Recomendación Estratégica

Mi recomendación: no compitamos con una app. Compitamos con una operación.

La idea ganadora debería ser:

> Un negocio educativo operado por agentes de IA que ayuda a docentes, bootcamps, tutores e instituciones pequeñas a crear, vender, ejecutar y corregir evaluaciones prácticas con feedback automático.

### Nombre Tentativo

**ClassOps AI**

**Subtítulo en inglés:**

> AI agents that run assessment operations for real educators. From lesson goals to graded evidence, feedback, reports, and student recovery plans.

**Subtítulo en español:**

> Agentes de IA que operan el ciclo completo de evaluación para docentes reales: creación, publicación, corrección, feedback, reportes y reforzamiento.

## Por Qué Esta Idea Tiene Más Opciones

Tienes una ventaja injusta: eres docente, desarrollador senior, conoces Spring Boot, APIs, evaluación, PSeInt, programación inicial, testing, rúbricas, feedback académico y el dolor real del profesor.

Además, el problema es medible. En Chile, TALIS 2024 reporta que docentes de jornada completa dedican **4,9 horas semanales** a marcar/corregir trabajos y **4,9 horas semanales** a trabajo administrativo, este último por sobre el promedio OCDE de **3 horas**.

Ese dato es oro para el pitch:

> ClassOps AI devuelve horas docentes cada semana, sin reemplazar al profesor: automatiza la operación repetitiva de evaluación y deja al humano tomando decisiones pedagógicas.

## Producto

ClassOps AI es una plataforma SaaS para docentes y pequeños equipos educativos que permite:

- Cargar un objetivo de clase, temario o guía.
- Generar una evaluación práctica.
- Generar rúbrica y criterios.
- Publicar la actividad a estudiantes.
- Recibir respuestas o evidencias.
- Corregir automáticamente cuando sea posible.
- Sugerir feedback individual.
- Detectar errores comunes.
- Crear actividades de recuperación.
- Preparar reportes para el docente.
- Automatizar comunicación con estudiantes.
- Registrar logs de cada decisión de IA.

No es solo "crear pruebas con IA". Eso está saturado.

La diferencia es que el negocio opera con agentes.

## Categoría Principal

**Education & Human Potential**

También tiene borde con **Small Business Services**, porque ayuda a docentes independientes, tutores y academias pequeñas a operar como una microinstitución educativa. Pero yo entraría por **Education & Human Potential**, porque tu historia, el impacto y el acceso a usuarios reales calzan mejor.

## Narrativa Para Jueces

Los jueces no van a comprar "una app para hacer evaluaciones".

Van a comprar esta narrativa:

> Millones de docentes y tutores no necesitan otro LMS complejo. Necesitan una operación educativa automatizada que les permita enseñar, evaluar y acompañar sin ahogarse en corrección y administración. ClassOps AI convierte a un docente en una microacademia operada por agentes.

Ese ángulo vende mejor porque toca tres puntos de la hackathon:

- **Business Viability:** docentes, tutores y bootcamps pueden pagar rápido por ahorrar tiempo.
- **AI-Native Operations:** los agentes toman decisiones operativas reales: generar evaluación, clasificar evidencias, corregir, priorizar alumnos, enviar feedback, crear reportes.
- **Category Impact:** mejora acceso a feedback personalizado y reduce carga docente.

Los criterios oficiales piden negocio real, usuarios reales, revenue, agentes en producción y evidencia de logs, uso de API, dashboards y clientes.

## MVP Ganador

No hagamos un monstruo. El MVP debe ser vendible, demostrable y cobrable en menos de 70 días.

### MVP v1

**AI Assessment Ops for Programming Teachers**

### Nicho Inicial

Docentes de programación inicial, bootcamps, tutores de informática y profesores que trabajan con pseudocódigo, Python, JavaScript, Java o fundamentos de algoritmos.

### Por Qué Este Nicho

- Lo conoces.
- Puedes conseguir usuarios rápido.
- El dolor es real.
- Las evidencias son fáciles de evaluar.
- Permite demos visuales potentes.
- Tiene impacto claro en educación y empleabilidad.

## Flujo MVP

### 1. Docente Crea Una Actividad

El docente escribe:

> Quiero evaluar condicionales, ciclos y funciones en estudiantes de primer semestre. Duración 90 minutos. Nivel básico.

El agente genera:

- Enunciado.
- Objetivos de aprendizaje.
- Rúbrica.
- Criterios de evaluación.
- Casos de prueba.
- Pauta de corrección.
- Feedback esperado por tipo de error.

### 2. Estudiante Responde

Puede responder de tres formas en MVP:

- Texto/código pegado en plataforma.
- Archivo `.txt`, `.java`, `.py`, `.js`.
- Respuesta manual simple.

Evitaría OCR en la primera fase, salvo que sea muy necesario. OCR suma complejidad y riesgo.

### 3. Agentes Corrigen

| Agente | Responsabilidad |
| --- | --- |
| Assessment Designer Agent | Genera actividad y rúbrica. |
| Rubric Validator Agent | Revisa coherencia, dificultad y criterios. |
| Submission Analyzer Agent | Analiza respuesta/código del estudiante. |
| Feedback Agent | Genera feedback pedagógico accionable. |
| Risk Detector Agent | Detecta alumnos con bajo desempeño o patrones de error. |
| Teacher Copilot Agent | Resume resultados y recomienda siguiente clase. |
| Business Ops Agent | Registra uso, prepara reportes, genera evidencia para clientes y hackathon. |

Esto es clave: la hackathon quiere ver negocio operado por IA, no solo IA dentro de una funcionalidad.

### 4. Docente Revisa Y Aprueba

Para evitar problemas de confianza:

- La IA sugiere.
- El docente aprueba.
- Se registra que hizo la IA y que corrigió el humano.

Esto te permite decir:

> AI operates the assessment workflow, while teachers retain pedagogical authority.

### 5. Plataforma Genera Reporte

Reporte por actividad:

- Promedio.
- Distribución.
- Errores frecuentes.
- Objetivos menos logrados.
- Estudiantes en riesgo.
- Actividad de reforzamiento sugerida.
- Mensaje personalizado para cada estudiante.

## Arquitectura Recomendada Para Competir

Como la hackathon exige Google Cloud, no basta con "uso Gemini API desde cualquier hosting". Las reglas dicen que el proyecto debe usar al menos un producto de Google Cloud y que los proyectos con LLM deben usar Gemini API para al menos una llamada en la app desplegada.

Arquitectura simple y defendible:

| Capa | Tecnología |
| --- | --- |
| Frontend | Next.js o Angular |
| Backend | Spring Boot o Node/NestJS |
| Hosting backend | Google Cloud Run |
| IA | Gemini API / Vertex AI Gemini |
| Logs | Cloud Logging |
| Base de datos | Firestore, Cloud SQL PostgreSQL o Supabase si se justifica |
| Storage | Cloud Storage para archivos |
| Pagos | Stripe |
| Auth | Firebase Auth o KeyGo si quieres usar algo propio, pero con cuidado |
| Observabilidad | Cloud Logging + dashboard interno |
| Video demo | Mostrar agentes ejecutando decisiones reales |

Cloud Run calza bien porque Google lo define como una plataforma completamente administrada para ejecutar contenedores invocables por requests o eventos, sin gestionar infraestructura.

Para los agentes, Gemini permite function calling y salidas estructuradas, útil para que la IA no devuelva solo texto libre, sino JSON validable para rúbricas, feedback, notas, riesgos y acciones.

## Evidencia Necesaria Para Vender

La entrega pide varias evidencias:

- Repo.
- Video de menos de 3 minutos.
- Narrativa de 500 a 1000 palabras.
- Evidencia de ingresos.
- Gastos.
- Logs de ejecución de agentes.
- Uso de API.
- Dashboards.
- Evidencia de clientes reales.

Por eso el producto debe tener desde el día 1 evidencia interna obligatoria.

### Logs Por Ejecución De Agente

Cada ejecución de agente debe guardar:

- Fecha/hora.
- Usuario/docente.
- Actividad.
- Agente ejecutado.
- Input recibido.
- Decisión tomada.
- Output estructurado.
- Modelo usado.
- Tokens/costo aproximado.
- Estado: sugerido, aprobado, corregido, rechazado.
- Impacto: minutos estimados ahorrados.

Esto sirve para la app, pero también para ganar.

## Modelo De Negocio

Necesitamos revenue rápido, no una proyección bonita.

### Pricing Recomendado

| Plan | Precio | Incluye |
| --- | ---: | --- |
| Free | US$0 | 3 evaluaciones, 20 estudiantes, marca de agua, sin reportes avanzados. |
| Teacher Pro | US$9/mes | 20 evaluaciones, 150 estudiantes/mes, feedback automático, reportes básicos. |
| Cohort Pro | US$29/mes | 100 evaluaciones, 500 estudiantes/mes, reportes por curso, exportación PDF/CSV, soporte prioritario. |
| Pilot Pack | US$99 pago único | Setup, 3 evaluaciones reales y reporte ejecutivo para bootcamp, docente independiente o pequeña academia. |

Para la hackathon, el mejor producto no es necesariamente el más escalable todavía. Es el que puede generar evidencia de pago en 70 días.

Yo apuntaría a vender **10 a 20 Pilot Packs** o **30 suscripciones Teacher Pro**.

Con eso ya puedes mostrar:

- Ingresos reales.
- Clientes reales.
- Uso real.
- Testimonios.
- Costos controlados.
- CAC bajo o cero.
- Validación clara.

## Go-To-Market En 70 Dias

### Mercado Inicial

No iría primero por colegios grandes ni universidades completas. Ciclos de venta lentos.

Iría por:

- Docentes independientes.
- Profesores de programación.
- Tutores.
- Bootcamps pequeños.
- Academias online.
- Coordinadores académicos con poder de piloto pequeño.
- Comunidades de profesores de informática.

Tu ventaja está en la red docente y técnica. El pitch debe ser directo:

> Te ahorro horas corrigiendo y te entrego feedback personalizado para tus estudiantes sin cambiar tu forma de enseñar.

### Oferta Comercial Inicial

No vender "software".

Vender:

> Piloto de corrección y feedback automático para tu próxima evaluación.

Landing:

- Sube tu pauta.
- Creamos actividad + rúbrica.
- Tus estudiantes responden.
- Recibes corrección, feedback y reporte.
- Tú apruebas antes de entregar.

Call to action:

> Run my next assessment with AI

## Demo De 3 Minutos

La demo debe vender como startup, no como tutorial técnico.

### Guion

| Tiempo | Bloque | Mensaje / Acción |
| --- | --- | --- |
| 0:00-0:20 | Dolor | "Teachers spend hours every week grading, correcting and preparing feedback. In Chile, full-time teachers report 4.9 hours per week marking student work and 4.9 hours on administrative work." |
| 0:20-0:40 | Solución | "ClassOps AI is an AI-native assessment operations platform. It helps educators create, run, grade and improve learning activities with AI agents." |
| 0:40-1:30 | Demo producto | Mostrar: docente crea actividad, agente genera evaluación, agente genera rúbrica, estudiante entrega respuesta, agente corrige, docente aprueba, se genera feedback y dashboard muestra resultados. |
| 1:30-2:10 | AI-native operations | Mostrar pantalla de logs: Assessment Designer Agent, Rubric Validator Agent, Feedback Agent, Risk Detector Agent, Teacher Copilot Agent, cada uno con estado y decisión. |
| 2:10-2:40 | Business traction | Mostrar usuarios reales, pagos Stripe, testimonios, revenue, costos y uso de Gemini/Google Cloud. |
| 2:40-3:00 | Cierre | "ClassOps AI turns every educator into an AI-operated learning business. Teachers stay in control. Students get better feedback. Small education providers can scale." |

## Lo Que No Debemos Hacer

No hagamos esto:

- Un chatbot para estudiantes.
- Un generador genérico de quizzes.
- Un LMS completo.
- Una plataforma enorme tipo Moodle con IA.
- Una app que solo "usa Gemini".
- Un proyecto sin pagos.
- Un proyecto sin logs.
- Un proyecto donde el humano hace todo y la IA solo redacta texto.
- Un proyecto viejo reciclado sin aclarar.

Ojo con esto último: las reglas dicen que los proyectos deben ser creados después del inicio de la hackathon, el **19 de mayo de 2026**. Se pueden usar templates, frameworks o boilerplates preexistentes, pero se debe explicar cómo se usaron.

Por tanto, no conviene presentar un proyecto anterior como si fuera nuevo. Conviene construir ClassOps AI desde cero, aunque esté inspirado en tu experiencia docente y en dolores que ya conoces.

## Diferenciador Fuerte

La mayoría va a presentar:

> AI tutor for students.

Nosotros deberíamos presentar:

> AI operations layer for educators.

Eso es más fuerte porque:

- Tiene comprador claro.
- Tiene dolor económico.
- Tiene uso recurrente.
- Tiene evidencia de ahorro de tiempo.
- Puede generar revenue rápido.
- Puede expandirse a instituciones.
- Encaja con "AI agents operating a business".

## Roadmap De Ejecución

### Semana 1: Validación Y Preventa

**Objetivo:** conseguir 5-10 docentes interesados antes de construir demasiado.

**Entregables:**

- Landing simple.
- Formulario de waitlist.
- Oferta de piloto pagado.
- 10 entrevistas.
- 3 pagos o compromisos.
- Definición del nicho exacto.

### Semana 2-3: MVP Funcional

**Entregables:**

- Login docente.
- Crear actividad.
- Generar rúbrica con Gemini.
- Cargar respuestas.
- Corrección asistida.
- Feedback individual.
- Logs de agentes.
- Dashboard básico.

### Semana 4-5: Pilotos Reales

**Entregables:**

- 5 actividades reales.
- 100+ respuestas procesadas.
- Testimonios.
- Métrica de tiempo ahorrado.
- Ajuste de pricing.
- Export PDF/CSV.

### Semana 6-7: Producto Vendible

**Entregables:**

- Stripe.
- Planes.
- Onboarding automático.
- Mejor dashboard.
- Reportes por curso.
- Emails automáticos.
- Página pública con casos reales.

### Semana 8-10: Hackathon Packaging

**Entregables:**

- Video de 3 minutos.
- Narrativa 500-1000 palabras.
- Repo limpio.
- Testing instructions.
- Revenue evidence.
- Expense report.
- Agent logs.
- Customer evidence.

## Métricas Que Debemos Perseguir

Para vender la historia:

| Métrica | Meta razonable |
| --- | ---: |
| Docentes registrados | 30-50 |
| Clientes pagados | 10-20 |
| Estudiantes evaluados | 200-500 |
| Evaluaciones creadas | 30-80 |
| Feedbacks generados | 300-1000 |
| Revenue | US$300-US$2000 |
| Tiempo docente ahorrado | 100+ horas estimadas |
| Agentes ejecutados | 1000+ eventos logueados |

No necesitas millones de usuarios. Necesitas una señal real, verificable y creíble.

## Pitch Final

> ClassOps AI helps educators run assessment workflows with AI agents. Teachers describe what they want to evaluate, and our agents generate the activity, rubric, correction criteria, feedback, recovery plan and performance report. Students get faster, more personalized feedback. Teachers stay in control. Small education providers can operate like full academic teams. In 90 days, we are proving this with real teachers, real students, real usage and real revenue.

## Veredicto

La mejor apuesta para ti es **ClassOps AI**, no porque sea la idea "más grande", sino porque es la más ganable para tu perfil.

Tienes dominio del problema, acceso natural a usuarios, capacidad técnica para construirlo, historia personal creíble, categoría clara, impacto real y posibilidad de vender rápido.

La hackathon no se gana diciendo:

> Mira lo que construí.

Se gana diciendo:

> Mira el negocio que ya está operando con IA, mira quién pagó, mira los logs, mira el impacto y mira por qué esto puede crecer.


---

## Source: `.raw/01-chat.md`

# GradeOps AI: Posicionamiento Para Hackathon

> Nota raw formateada desde la segunda conversación estratégica.

> Decisión posterior: este archivo consolida el giro desde GRADE/ClassOps hacia **GradeOps AI** como marca principal para la hackathon.

## Tesis

Sí. Tu cabeza hizo la conexión correcta: esto es **GRADE**.

Pero para la hackathon no lo presentaría como "GRADE" en su versión académica amplia. Lo presentaría como una versión más filosa, vendible y operada por IA:

**GRADE Ops AI**

> AI-native assessment operations for educators, tutors and small academies.

O en español:

> Operación inteligente de evaluaciones para docentes, tutores y academias pequeñas.

La idea no cambia de fondo. Lo que cambia es el empaquetado comercial.

## Diferencia Estratégica

| GRADE original | Versión hackathon |
| --- | --- |
| Plataforma para generar, registrar y calificar evaluaciones. | Negocio operativo de evaluación asistido por agentes IA. |
| Foco en sistema académico. | Foco en clientes reales y revenue. |
| Puede sonar institucional/complejo. | SaaS liviano, vendible y demostrable. |
| Banco de preguntas, OCR, reportes, calificación. | "Te opero tu próxima evaluación completa con IA". |
| Producto educativo. | Microempresa AI-native para docentes. |

## La Frase Clave

No deberíamos decir:

> Creamos una plataforma para docentes.

Deberíamos decir:

> GRADE Ops AI permite que un docente opere como un equipo académico completo: diseña evaluaciones, corrige, entrega feedback, detecta brechas y genera acciones de reforzamiento usando agentes IA.

Eso vende mucho más.

## Cómo Encaja GRADE Con La Hackathon

GRADE ya tiene los componentes naturales:

- Generación de evaluaciones.
- Banco de preguntas.
- Rúbricas.
- Calificación automática.
- Feedback.
- Reportes.
- Trazabilidad.
- Mejora pedagógica.

Pero para ganar, necesitamos elevarlo a:

- Agentes IA ejecutando operaciones.
- Clientes reales.
- Pagos reales.
- Evidencia de uso.
- Impacto medible.
- Demo simple y poderosa.
- Narrativa de negocio.

## Decisión Estratégica

Yo no iría por todo GRADE.

Iría por este wedge:

> GRADE Ops AI para docentes de programación inicial.

Porque ahí tienes ventaja brutal.

Puedes decir:

> We started with programming educators because code-based assessments are frequent, time-consuming to grade, and require personalized feedback. Our agents help teachers generate, grade and improve practical programming assessments.

En español:

> Partimos con docentes de programación porque las evaluaciones prácticas consumen mucho tiempo, requieren revisión caso a caso y necesitan feedback personalizado.

Esto calza perfecto contigo.

## MVP Específico

### Nombre Interno

**GRADE Ops AI**

### Nombres Comerciales Posibles

- GradeOps AI.
- GRADE AI.
- ClassOps AI.
- EvalOps AI.
- AssessOps AI.

Mi favorito para la hackathon: **GradeOps AI**.

Suena startup, suena operación, suena vendible.

### Promesa Comercial

> Run your next assessment with AI agents.

O:

> From learning goal to graded feedback in minutes.

En español:

> De objetivo de aprendizaje a feedback corregido en minutos.

## Flujo MVP Ganador

### 1. El Docente Crea Una Evaluación

**Input:**

> Quiero evaluar condicionales, ciclos y funciones en Java para estudiantes de primer semestre.

**GRADE Ops genera:**

- Enunciado.
- Objetivos.
- Criterios.
- Rúbrica.
- Casos de prueba.
- Pauta.
- Nivel de dificultad.
- Tiempo estimado.

### 2. El Estudiante Responde

MVP simple:

- Pega código.
- Sube archivo.
- Responde formulario.
- Adjunta evidencia.

Nada de OCR al inicio, salvo que lo dejemos como "futuro inmediato".

### 3. Agentes IA Procesan

| Agente | Función |
| --- | --- |
| Assessment Agent | Diseña evaluación y rúbrica. |
| Rubric Agent | Valida criterios y consistencia. |
| Grading Agent | Evalúa respuesta contra rúbrica. |
| Feedback Agent | Genera feedback individual. |
| Learning Gap Agent | Detecta brechas comunes. |
| Recovery Agent | Propone actividades de reforzamiento. |
| Teacher Report Agent | Genera resumen ejecutivo para el docente. |
| Ops Agent | Registra logs, costos, métricas y evidencia de operación. |

### 4. El Docente Aprueba

Esto es importante:

- La IA no reemplaza al docente.
- La IA opera el flujo.
- El docente conserva autoridad pedagógica.

Eso reduce fricción comercial.

### 5. Dashboard Final

Mostrar:

- Promedio.
- Distribución.
- Estudiantes en riesgo.
- Errores frecuentes.
- Objetivos menos logrados.
- Tiempo estimado ahorrado.
- Feedback enviado.
- Actividad remedial sugerida.

## La Trampa Que Debemos Evitar

No presentar GRADE como:

> Sistema de gestión de evaluaciones académicas.

Eso suena grande, pesado, institucional y lento de vender.

Presentarlo como:

> AI agents that run assessment operations for real educators.

Eso suena directo, moderno, vendible y alineado con la hackathon.

## Pitch Refinado

**Versión en inglés:**

> GradeOps AI helps educators run practical assessments with AI agents. A teacher enters a learning goal, and our agents generate the assessment, rubric, grading criteria, personalized feedback, learning gap analysis and recovery activities. Teachers stay in control, students receive faster feedback, and small education providers can operate like full academic teams without hiring more staff.

**Versión en español:**

> GRADE Ops AI ayuda a docentes a operar evaluaciones prácticas con agentes de IA. El docente ingresa un objetivo de aprendizaje y los agentes generan la evaluación, rúbrica, criterios de corrección, feedback personalizado, análisis de brechas y actividades de reforzamiento. El docente mantiene el control, los estudiantes reciben mejor retroalimentación y pequeños equipos educativos pueden operar como una institución completa sin aumentar carga administrativa.

## Qué Parte De GRADE Usaría Para Competir

### Núcleo Ganador

- Crear evaluación.
- Crear rúbrica.
- Recibir respuestas.
- Corregir.
- Generar feedback.
- Generar reporte.
- Registrar trazabilidad de agentes.
- Cobrar por piloto.

### Fuera Del MVP

- OCR complejo.
- Banco de preguntas gigante.
- Integración institucional.
- LMS completo.
- Múltiples roles avanzados.
- Mobile app.
- Analítica excesiva.
- Administración curricular completa.

Eso puede ir en roadmap, pero no en el producto inicial.

## Conclusión Directa

Sí: esto es **GRADE**.

Pero para ganar, GRADE debe vestirse así:

> GRADE no es una plataforma de evaluación. Es una operación académica automatizada por agentes IA.

Ese giro es el que puede vender.

Mi recomendación: trabajemos desde ahora con este posicionamiento:

**GradeOps AI**

> AI-native assessment operations for programming educators.

Ese es el wedge más defendible, más rápido de construir, más fácil de vender y más coherente con tu experiencia.


---

## Source: `.raw/02-chat.md`

# Lectura Estratégica Del Artículo TodoDeIA

> Nota raw formateada desde la conversación sobre el artículo: <https://www.tododeia.com/community/gemini-xprize>

## Prompt Original

> Lee en profundidad este artículo: <https://www.tododeia.com/community/gemini-xprize>

## Enfoque De Lectura

Voy a leer el artículo como insumo estratégico para **GradeOps AI**:

- reglas y criterios;
- señales de oportunidad;
- riesgos;
- cambios respecto a lo que ya definimos.

Primer hallazgo fuerte: el artículo está bien orientado comercialmente, pero hay que leerlo junto a las reglas oficiales. La palabra clave no es "app"; es **negocio verificable operado por IA**.

## Lectura Estratégica

Ya lo leí en profundidad. Mi lectura estratégica: el artículo confirma exactamente el giro que necesitamos para **GradeOps AI**:

> No competir como "plataforma educativa", sino como negocio real de operación académica automatizada por agentes IA.

## Tesis Central Del Artículo

El artículo no está vendiendo una hackathon técnica. Está diciendo:

> Gana quien monte un negocio real, con clientes reales, ingresos reales y operación ejecutada por IA.

Esa lectura coincide con las reglas oficiales:

- el proyecto debe operar con IA;
- debe usar al menos un producto de Google Cloud;
- si usa LLM, debe hacer al menos una llamada a Gemini API en la aplicación desplegada.

La idea más importante del artículo es:

> No gana la idea más bonita; gana el que vende de verdad.

Devpost lo confirma con el enfoque:

> Real product. Real revenue. A real business.

Los criterios oficiales ponderan:

- **Business Viability**;
- **AI-Native Operations**;
- **Category Impact**.

## Lo Más Importante Para GradeOps AI

Para **GradeOps AI**, el artículo refuerza que no debemos partir vendiendo:

> Sistema de generación y corrección de evaluaciones.

Eso suena a software académico tradicional.

Debemos vender:

> AI-native assessment operations for programming educators.

O en español:

> Operación de evaluaciones prácticas con agentes IA para docentes de programación.

Esto calza con lo que ya habíamos detectado en la lectura previa:

- la competencia premia una mini startup operando;
- no premia solo una demo con IA;
- la versión hackathon debe ser enfocada, vendible y con revenue verificable.

## Reglas Críticas Que No Podemos Fallar

Estos puntos deben pasar a checklist obligatorio del repo de documentación:

| Regla | Implicancia Para GradeOps AI |
| --- | --- |
| Proyecto nuevo | Debe haber sido creado después del inicio del concurso: **19 de mayo de 2026**. Se pueden usar frameworks, templates o boilerplates, pero hay que explicar cómo se usaron. |
| Google Cloud obligatorio | No basta con usar Gemini desde cualquier hosting. Debe usarse al menos un producto de Google Cloud. Cloud Run, Firebase, Firestore, BigQuery o Vertex AI cuentan. |
| Gemini API obligatorio si usamos LLM | Podemos usar otros modelos además, pero al menos una llamada LLM en la app desplegada debe usar Gemini API. |
| Revenue real y desglosado | Piden revenue total en USD, revenue por mes —mayo, junio, julio y agosto 2026—, costos, gasto de marketing/adquisición y evidencia financiera. |
| Cuidado con ingresos de conocidos | El revenue de familiares, miembros del equipo, entidades relacionadas o relaciones comerciales preexistentes debe reportarse separado. Para vender fuerte necesitamos clientes *arms-length*: terceros reales sin relación directa. |
| Evidencia de producto operando | Logs de agentes, registros de uso de API, dashboards y capturas. Esto no es accesorio; es parte del caso de negocio. |
| Video menor a 3 minutos | Los jueces no están obligados a mirar más allá de tres minutos. Debe mostrar el producto funcionando en el dispositivo/plataforma real. |
| Material en inglés o traducido | Si enviamos material en español, hay que proveer traducción al inglés del video, descripción, testing instructions y demás materiales. |

## Lectura Crítica Del Artículo

El artículo está bien como playbook, pero tiene un sesgo sano:

> Empuja a vender antes de construir demasiado.

Para nosotros eso significa que el primer entregable no debe ser una arquitectura perfecta, sino una máquina de evidencia:

- landing;
- propuesta de piloto pagado;
- formulario de clientes;
- flujo mínimo de evaluación;
- Stripe o mecanismo equivalente de pago;
- logs de agentes desde el día 1;
- dashboard interno de uso, costos y tiempo ahorrado.

El artículo también insiste en que la IA debe operar el negocio, no solo asistir. Esto es consistente con el criterio oficial **AI-Native Operations**:

- IA en producción;
- decisiones clave ejecutadas por agentes;
- operación ampliamente gobernada por IA;
- evidencia observable de esa operación.

## Qué Cambia Para GradeOps AI

No cambia la idea. Cambia la prioridad.

### Antes Podíamos Pensar En

- banco de preguntas;
- OCR;
- mobile app;
- reportes avanzados;
- integración institucional;
- administración académica completa.

### Ahora La Prioridad Debe Ser

1. Crear evaluación desde objetivo de aprendizaje.
2. Generar rúbrica estructurada.
3. Recibir entrega del estudiante.
4. Corregir con agente IA.
5. Generar feedback individual.
6. Detectar brechas comunes.
7. Proponer recuperación.
8. Mostrar reporte docente.
9. Registrar trazabilidad completa de agentes.
10. Cobrar por piloto real.

OCR, mobile app, LMS, banco gigante y analítica avanzada deben quedar fuera del MVP de hackathon.

## Stack Recomendado Después De Leer El Artículo

Para maximizar cumplimiento y velocidad:

| Capa | Decisión recomendada |
| --- | --- |
| Frontend | Next.js o Angular |
| Backend | Spring Boot si quieres mantener ventaja técnica, o Node/NestJS si priorizamos velocidad con agentes JS |
| Deploy | Google Cloud Run |
| IA | Gemini API, modelo base `gemini-3.5-flash` |
| Agentes | ADK o una capa propia de orquestación con logs claros |
| Datos | Firestore o Cloud SQL PostgreSQL |
| Archivos | Cloud Storage |
| Auth | Firebase Auth o auth simple propia para MVP |
| Pagos | Stripe |
| Evidencia | Agent Execution Log + API Usage Log + Revenue Evidence |

Gemini soporta function calling y structured outputs, lo que sirve para que los agentes no devuelvan solo texto, sino JSON validable para:

- rúbricas;
- notas;
- feedback;
- brechas;
- acciones.

## Veredicto

El artículo confirma que **GradeOps AI** es una buena apuesta, pero solo si lo empaquetamos como negocio operativo, no como sistema académico.

La formulación ganadora debería ser:

> GradeOps AI helps programming educators run practical assessments with AI agents. Teachers enter a learning goal; our agents generate the assessment, rubric, grading criteria, feedback, learning gap analysis and recovery activities. Teachers stay in control, students receive faster feedback, and small education providers can operate like full academic teams.

La decisión táctica inmediata:

> No construir "todo GradeOps". Construir el flujo que pueda venderse esta semana como: "Te opero tu próxima evaluación práctica con IA: diseño, rúbrica, corrección, feedback y reporte."


---

## Source: `.raw/03-chat.md`

# Lectura Técnica Del Artículo TodoDeIA

> Nota raw formateada desde la conversación técnica sobre el artículo: <https://www.tododeia.com/community/gemini-xprize>

> Decisión posterior: este archivo conserva una exploración técnica. La política canónica actual está en `../solution.md` y `../cost-model.md`: usar model routing, no usar suscripciones personales como runtime productivo y verificar precios/modelos oficiales antes de desplegar o postular.

## Prompt Original

> Ok, genial eso. ¿Y la parte técnica de la que habla? Te dejo el enlace nuevamente: <https://www.tododeia.com/community/gemini-xprize>

## Tesis Técnica

La parte técnica del artículo básicamente dice:

> No basta con usar Gemini como "chatbot" dentro de la app; hay que montar una arquitectura donde Gemini + agentes + herramientas + logs + cloud formen el núcleo operativo del negocio.

Para **GradeOps AI**, esto significa que el producto debe demostrar operación, no solo generación de texto.

## 1. Gemini API: Requisito Mínimo, No Diferenciador

El artículo dice que la app desplegada debe:

- hacer al menos una llamada a Gemini API;
- usar al menos un producto de Google Cloud.

Eso es requisito de entrada, no ventaja competitiva.

Para nosotros, Gemini no debería usarse solo para:

> Genera una evaluación.

Debe usarse para varias operaciones reales:

| Operación | Uso De Gemini |
| --- | --- |
| Crear evaluación | Generar enunciado, objetivos e instrucciones. |
| Crear rúbrica | Devolver criterios estructurados. |
| Validar rúbrica | Detectar ambigüedad o dificultad mal calibrada. |
| Analizar entrega | Revisar código/respuesta del estudiante. |
| Corregir | Aplicar rúbrica y sugerir puntaje. |
| Generar feedback | Crear feedback individual accionable. |
| Detectar brechas | Agrupar errores frecuentes. |
| Recomendar recuperación | Sugerir actividad remedial. |
| Generar reporte | Preparar resumen ejecutivo para el docente. |

La diferencia clave:

> Cada operación debe quedar registrada como evento de agente.

## 2. Function Calling: Base Real De Los Agentes

El artículo menciona function calling como "la base de un agente".

Técnicamente, esto significa que Gemini no solo responde texto: puede decidir llamar funciones de negocio con parámetros estructurados. La documentación oficial de Gemini lo define como una forma de conectar el modelo con herramientas y APIs externas para ejecutar acciones reales.

Para **GradeOps AI**, las tools no deberían ser genéricas como `buscar()` o `guardar()`. Deberían representar acciones reales del dominio:

- `create_assessment()`;
- `create_rubric()`;
- `validate_rubric()`;
- `grade_submission()`;
- `generate_feedback()`;
- `detect_learning_gaps()`;
- `create_recovery_activity()`;
- `generate_teacher_report()`;
- `record_agent_execution()`.

Eso permite decir ante los jueces:

> Nuestros agentes no solo redactan contenido; ejecutan operaciones académicas completas.

## 3. Structured Output: Obligatorio Para Que Esto Sea Sistema

El artículo insiste en salida estructurada con JSON. Esto es crítico para nosotros.

### Mala Implementación

> Gemini responde un párrafo con la rúbrica.

### Buena Implementación

```json
{
  "rubric": [
    {
      "criterion": "Uso correcto de condicionales",
      "maxScore": 25,
      "levels": [
        {
          "label": "Logrado",
          "score": 25,
          "description": "Implementa condicionales correctamente..."
        }
      ]
    }
  ]
}
```

La documentación oficial de Gemini confirma soporte de structured outputs, incluyendo combinación con herramientas en modelos Gemini 3.

Para **GradeOps AI**, esto es fundamental porque necesitamos guardar:

- rúbricas;
- puntajes;
- feedback;
- brechas;
- riesgos;
- decisiones;
- costos;
- logs;
- reportes.

Sin JSON estructurado, después todo se vuelve frágil.

## 4. ADK: Útil, Pero No Obligatorio Para Todo

El artículo habla de Google ADK, el Agent Development Kit. ADK es el framework open-source de Google para construir, depurar y desplegar agentes IA; hoy soporta Python, TypeScript, Go, Java y Kotlin.

Mi lectura para **GradeOps AI**:

> Sí conviene usar ADK, pero con foco. No intentaría meter toda la plataforma dentro de ADK.

Separación recomendada:

| Pieza | Tecnología recomendada |
| --- | --- |
| Web app | Next.js |
| API principal | Spring Boot o Next.js API |
| Agentes IA | ADK, idealmente Python o TypeScript |
| Modelo | Gemini 3.5 Flash como base |
| Deploy | Cloud Run |
| Datos | Firestore o PostgreSQL |
| Archivos | Cloud Storage |
| Auth | Firebase Auth |
| Pagos | Stripe |
| Evidencia | Agent logs + dashboard interno |

ADK debería operar el flujo de agentes, no reemplazar toda la arquitectura.

## 5. Cloud Run: Opción Más Limpia Para Cumplir Google Cloud

El artículo propone Cloud Run o Firebase. Para nuestro caso, Cloud Run es la opción más defendible porque permite desplegar contenedores backend/agent sin administrar infraestructura.

La documentación oficial de ADK indica que los agentes pueden desplegarse en Cloud Run con `adk deploy cloud_run` o con `gcloud run deploy`.

### Arquitectura Mínima Defendible

```text
Usuario docente
   ↓
Next.js Web App
   ↓
GradeOps API
   ↓
Agent Orchestrator
   ↓
Gemini API + Tools
   ↓
Firestore / PostgreSQL / Cloud Storage
   ↓
Agent Execution Logs + Dashboard
```

Para la hackathon, esto cumple:

- llamada real a Gemini;
- uso real de Google Cloud;
- agentes operando flujo principal;
- datos persistidos;
- evidencia verificable.

## 6. Grounding Con Google Search: Usarlo Con Cuidado

El artículo menciona grounding con Google Search para datos frescos. La documentación oficial indica que conecta Gemini con contenido web en tiempo real y permite respuestas con fuentes verificables.

Para **GradeOps AI**, no lo usaría en la corrección de estudiantes. Ahí necesitamos consistencia, no búsqueda web.

Sí lo usaría para:

- sugerir ejemplos actualizados;
- generar contexto de una actividad;
- buscar referencias públicas;
- construir material complementario;
- enriquecer actividades de recuperación.

No debería usarse para decidir una nota.

## 7. Multimodal: Potente, Pero No Para El MVP Inicial

El artículo destaca que Gemini entiende texto, imagen, audio y video. Técnicamente es relevante, pero para **GradeOps AI** no metería OCR ni corrección desde foto en el MVP.

Por ahora:

> MVP = texto + código pegado + archivo subido.

Roadmap:

> V2 = imagen/foto/OCR de respuestas manuscritas.

Motivo: el MVP debe vender rápido y ser confiable. Meter OCR ahora aumenta riesgo técnico, validación y tiempo de QA.

## 8. Gemini CLI / Claude Code: Herramienta De Construcción, No Parte Del Producto

El artículo dice algo importante:

> El concurso no obliga a programar con Gemini CLI; obliga a que el producto desplegado llame a Gemini y use Google Cloud.

Eso para nosotros significa:

- podemos construir con Claude Code, Codex, IntelliJ, VSCode o lo que convenga;
- lo importante es que GradeOps AI en producción use Gemini;
- el repo debe dejar claro qué fue generado con IA y qué fue diseñado por el equipo.

Yo usaría agentes de código para acelerar, pero dejaría decisiones técnicas documentadas en `grade-ops-ai-docs`.

## 9. La Parte Técnica Que Más Conviene Copiar

La frase técnica más valiosa:

> La IA debe operar el negocio, no asistirlo.

Bajado a **GradeOps AI**:

### No

> El docente pide ayuda a una IA para crear una prueba.

### Sí

> El docente inicia una operación de evaluación. Los agentes diseñan, validan, corrigen, generan feedback, detectan brechas, preparan recuperación, registran evidencia y dejan todo listo para aprobación humana.

Ese enfoque debe reflejarse en la arquitectura.

## 10. Diseño Técnico Recomendado Para GradeOps AI

Mi recomendación concreta:

```text
grade-ops-ai-docs
grade-ops-ai-web
grade-ops-ai-api
grade-ops-ai-agents
grade-ops-ai-infra
```

### `grade-ops-ai-web`

**Tecnología:** Next.js.

**Responsabilidades:**

- landing;
- login docente;
- dashboard;
- crear evaluación;
- ver entregas;
- aprobar correcciones;
- ver reportes;
- ver logs de agentes en modo demo.

### `grade-ops-ai-api`

**Tecnología:** Spring Boot si queremos aprovechar ventaja técnica.

**Responsabilidades:**

- usuarios;
- cursos;
- evaluaciones;
- entregas;
- rúbricas;
- reportes;
- seguridad;
- persistencia;
- endpoints para la web;
- integración con agentes.

### `grade-ops-ai-agents`

**Tecnología:** ADK o implementación agentic propia.

**Responsabilidades:**

- Assessment Agent;
- Rubric Agent;
- Grading Agent;
- Feedback Agent;
- Learning Gap Agent;
- Recovery Agent;
- Teacher Report Agent;
- Ops Agent.

### `grade-ops-ai-infra`

**Tecnología:** Terraform o scripts simples.

**Responsabilidades:**

- Cloud Run;
- Cloud Storage;
- variables de entorno;
- deploy;
- secrets;
- observabilidad.

## Veredicto Técnico

La parte técnica del artículo no debe interpretarse como:

> Usa todas las features de Gemini.

Debe interpretarse como:

> Construye un flujo donde Gemini + agentes + tools + JSON + logs + Cloud Run ejecuten una operación de negocio medible.

Para **GradeOps AI**, eso significa que el MVP técnico no es "generador de pruebas".

El MVP técnico es:

> Un motor agentic de operación evaluativa: recibe objetivo, genera evaluación, genera rúbrica, recibe respuestas, corrige, entrega feedback, detecta brechas, propone recuperación, registra trazabilidad y muestra evidencia de uso real.

Esa es la arquitectura que sí calza con la hackathon.


---

## Source: `.raw/04-chat.md`

# Costos, Créditos Y Pricing Para GradeOps AI

> Nota raw formateada desde la conversación sobre costos de desarrollo, operación y pricing para la hackathon.

> Decisión posterior: este archivo conserva la estimación original. La fuente canónica de pricing, unit economics y reporting financiero es `../cost-model.md`.

## Prompt Original

> Me queda una duda importantísima, sobre cómo costear este desarrollo. Como hay que utilizar servicios de Google y Gemini, eso no es gratis. ¿Qué dice el artículo original de la hackathon (<https://xprize.devpost.com>) al respecto? Por otra parte, estima detalladamente los costos de desarrollo y de operación para poder saber bien cuánto cobrar por las suscripciones.

## Enfoque De Respuesta

Voy a separar la respuesta en dos partes:

1. Qué dicen las bases originales sobre costos, créditos e ingresos.
2. Una estimación práctica de desarrollo, operación y precios para **GradeOps AI**.

Hallazgo concreto desde las bases:

> Sí hablan de costos, pero no como "te damos todo gratis". Piden reportar **Total Costs** y marketing por separado, lo que obliga a diseñar unit economics desde ahora.

## Conclusión Ejecutiva

No podemos tratar Google/Gemini como "gratis", aunque existan créditos y free tiers.

Para ganar la hackathon necesitamos demostrar negocio real, y eso incluye:

- costos reales;
- margen bruto;
- pricing defendible;
- evidencia financiera;
- costos operativos trazables.

## 1. Qué Dice El Artículo Oficial Sobre Costos

Las reglas oficiales de Devpost dicen tres cosas importantes:

1. Hay créditos gratuitos disponibles, pero no dice que todo sea gratis ni ilimitado. La regla indica que hay *free credits* accesibles en sitios relevantes para Google AI Ultra y Google Cloud.
2. Es obligatorio usar al menos un producto de Google Cloud, y si el proyecto usa LLM, debe hacer al menos una llamada a Gemini API en la aplicación desplegada.
3. La postulación exige reportar costos, no solo ingresos. Devpost pide declarar:
   - revenue total;
   - revenue por mes;
   - **Total Costs** excluyendo marketing;
   - **Marketing and Customer Acquisition Spend** por separado, incluso si el gasto de marketing fue cero.

La lectura correcta:

> La hackathon no te pide gastar mucho. Te pide demostrar que sabes cuánto cuesta operar tu negocio y que el modelo puede sostenerse.

Además, las reglas piden evidencia del producto corriendo:

- logs de agentes;
- registros de uso de API;
- screenshots de dashboards;
- evidencia que fortalezca el caso de que la operación está en producción.

## 2. Cuidado Con Los Créditos

No todos los créditos cubren Gemini API.

Google Cloud tiene una prueba gratuita de **US$300 por 90 días**, pero hay una advertencia crítica: la documentación oficial dice que ese crédito no puede usarse para pagar costos de Gemini API en AI Studio. Para Gemini API en AI Studio se debe considerar el free tier de Gemini o un plan de facturación/prepago propio de Gemini API.

Por otro lado, Google anunció créditos mensuales para suscriptores de Google AI Pro y Ultra:

- **US$10/mes** para AI Pro;
- **US$100/mes** para AI Ultra;
- integrados como beneficios de Google Developer Program.

Google indica que esos créditos pueden usarse para desplegar y escalar en:

- Cloud Run;
- Vertex AI;
- Gemini API vía AI Studio o Vertex AI, según disponibilidad y condiciones del beneficio.

### Recomendación Operativa

> No diseñar el negocio dependiendo de créditos.

Usarlos para reducir caja durante la hackathon, pero calcular precios como si tuviéramos que pagar todo.

## 3. Costos Base De Gemini Para GradeOps AI

Para el MVP, usaría **model routing**:

| Uso | Modelo recomendado | Motivo |
| --- | --- | --- |
| Generar evaluación | Gemini 3 Flash o 3.5 Flash | Mejor calidad pedagógica. |
| Generar rúbrica | Gemini 3 Flash o 3.5 Flash | Requiere consistencia. |
| Corregir entregas masivas | Gemini 3.1 Flash-Lite | Bajo costo por volumen. |
| Feedback individual | Gemini 3.1 Flash-Lite / Gemini 3 Flash | Mucho volumen. |
| Reporte docente | Gemini 3 Flash | Buena relación calidad/costo. |
| Casos complejos | Gemini 3.5 Flash | Solo fallback. |

Precios oficiales usados para estimar:

| Modelo | Input / 1M tokens | Output / 1M tokens |
| --- | ---: | ---: |
| Gemini 3.1 Flash-Lite | US$0.25 | US$1.50 |
| Gemini 3 Flash Preview | US$0.50 | US$3.00 |
| Gemini 3.5 Flash | US$1.50 | US$9.00 |

## 4. Estimación Por Evaluación Real

Unidad de negocio:

> 1 evaluación = creación de actividad + rúbrica + corrección de 30 estudiantes + feedback + reporte docente.

Supuesto técnico razonable por evaluación:

| Operación | Input tokens estimados | Output tokens estimados |
| --- | ---: | ---: |
| Crear actividad + rúbrica | 15.000 | 8.000 |
| Validar rúbrica | 10.000 | 2.000 |
| Corregir 30 entregas | 480.000 | 150.000 |
| Reporte final docente | 40.000 | 8.000 |
| **Total** | **545.000** | **168.000** |

Costo estimado por evaluación de 30 estudiantes:

| Modelo usado | Costo IA estimado | Con 25% de margen por retries/logs |
| --- | ---: | ---: |
| Gemini 3.1 Flash-Lite | US$0.39 | US$0.49 |
| Gemini 3 Flash Preview | US$0.78 | US$0.97 |
| Gemini 3.5 Flash | US$2.33 | US$2.91 |

Traducción directa:

- Con buen routing, una evaluación completa de 30 estudiantes debería costar entre **US$0.50 y US$1.20** en IA.
- Si usamos Gemini 3.5 Flash para todo, sube a cerca de **US$3** por evaluación.

El riesgo no está en una evaluación. El riesgo está en permitir uso ilimitado.

## 5. Costo Por Estudiante Corregido

Supuesto por estudiante:

> análisis + corrección + feedback.

| Modelo | Costo estimado por estudiante |
| --- | ---: |
| Gemini 3.1 Flash-Lite | US$0.014 |
| Gemini 3 Flash Preview | US$0.029 |
| Gemini 3.5 Flash | US$0.086 |

Esto nos dice algo importante:

> La suscripción debe limitar cantidad de entregas corregidas, no solo cantidad de evaluaciones.

Un plan que diga "evaluaciones ilimitadas" es peligroso.

Lo correcto es vender créditos:

- evaluaciones;
- estudiantes;
- correcciones incluidas;
- sobreuso por entrega adicional.

## 6. Costos De Google Cloud Para El MVP

Para un MVP liviano, Google Cloud puede salir barato si usamos:

- Cloud Run;
- Firestore;
- Cloud Storage;
- Cloud Logging;
- límites controlados.

### Cloud Run

Cloud Run cobra por recursos usados y tiene free tier mensual. En la tabla oficial, el free tier considera los primeros **240.000 vCPU-seconds** y **450.000 GiB-seconds** mensuales, dependiendo de región y configuración.

Para la hackathon, con tráfico bajo/medio:

| Concepto | Estimación mensual |
| --- | ---: |
| Cloud Run API backend | US$0-15 |
| Cloud Run agent worker | US$0-20 |
| Egress bajo | US$0-5 |
| **Subtotal Cloud Run** | **US$0-40/mes** |

### Firestore

Firestore tiene free quota:

- 1 GiB almacenado;
- 50.000 lecturas/día;
- 20.000 escrituras/día;
- 20.000 deletes/día;
- 10 GiB/mes de salida.

Después, por ejemplo, cobra US$0.03 por 100.000 reads y US$0.09 por 100.000 writes en la tabla mostrada para regiones listadas.

Para MVP:

| Concepto | Estimación mensual |
| --- | ---: |
| Firestore lecturas/escrituras | US$0-10 |
| Firestore storage | US$0-5 |
| **Subtotal Firestore** | **US$0-15/mes** |

### Cloud Storage

Cloud Storage tiene uso gratuito hasta ciertos límites, por ejemplo **5 GB-months** en Always Free. Para operaciones, Google lista costos como **US$0.005 por 1.000 operaciones Class A** en Standard Storage regional.

Para MVP sin OCR pesado:

| Concepto | Estimación mensual |
| --- | ---: |
| Archivos subidos por estudiantes | US$0-5 |
| Descargas/reportes | US$0-5 |
| **Subtotal Storage** | **US$0-10/mes** |

### Cloud Logging

Cloud Logging permite los primeros **50 GiB/proyecto/mes** sin cobro para logging storage; luego cobra **US$0.50/GiB**.

Para MVP:

| Concepto | Estimación mensual |
| --- | ---: |
| Logs técnicos | US$0 |
| Logs de agentes estructurados | Mejor guardarlos también en Firestore/DB |
| **Subtotal Logging** | **US$0-5/mes** |

### Artifact Registry Y Builds

Artifact Registry ofrece hasta **0.5 GB gratis** y luego **US$0.10/GB/mes**. Firebase también muestra Cloud Build con no-cost hasta **120 min/día** y luego **US$0.003/min**.

Para MVP:

| Concepto | Estimación mensual |
| --- | ---: |
| Artifact Registry | US$0-2 |
| Cloud Build | US$0-5 |
| **Subtotal DevOps** | **US$0-7/mes** |

## 7. Costo Mensual Total De Operación

### Escenario A: MVP Hackathon Controlado

Supuesto:

- 20 docentes registrados;
- 10 docentes activos;
- 50 evaluaciones reales/mes;
- 1.500 estudiantes corregidos/mes;
- model routing barato: Flash-Lite + Flash;
- sin OCR;
- sin búsqueda web en cada corrección.

| Categoría | Estimación mensual |
| --- | ---: |
| Gemini API | US$25-80 |
| Cloud Run | US$0-40 |
| Firestore | US$0-15 |
| Cloud Storage | US$0-10 |
| Cloud Logging | US$0-5 |
| Build/Artifact Registry | US$0-7 |
| Email/transaccional | US$0-15 |
| Dominio amortizado | US$1-3 |
| **Total operación mensual** | **US$26-175** |

Para la hackathon, presupuestaría **US$150-250/mes** aunque esperemos gastar menos. Eso evita sorpresas.

### Escenario B: Piloto Más Serio

Supuesto:

- 50 docentes;
- 25 docentes activos;
- 200 evaluaciones/mes;
- 6.000 estudiantes corregidos/mes;
- algunos casos usan Gemini 3.5 Flash como fallback.

| Categoría | Estimación mensual |
| --- | ---: |
| Gemini API | US$120-450 |
| Cloud Run | US$20-100 |
| Firestore | US$10-40 |
| Storage | US$5-30 |
| Logging/Monitoring | US$0-25 |
| Email | US$10-50 |
| **Total operación mensual** | **US$165-695** |

### Escenario C: SaaS Inicial Real

Supuesto:

- 200 docentes;
- 100 docentes activos;
- 1.000 evaluaciones/mes;
- 30.000 estudiantes corregidos/mes.

| Categoría | Estimación mensual |
| --- | ---: |
| Gemini API | US$600-2.500 |
| Cloud Run | US$100-400 |
| Firestore/DB | US$40-200 |
| Storage | US$20-100 |
| Logging/Monitoring | US$25-100 |
| Email | US$50-200 |
| Soporte operativo | US$300-1.500 |
| **Total operación mensual** | **US$1.135-5.000** |

En ese punto ya no basta un precio barato. Ahí necesitas planes por volumen.

## 8. Costos De Desarrollo

Hay dos formas de mirarlo.

### Caja Real Durante Hackathon

Si tú desarrollas gran parte y usas herramientas gratuitas/créditos:

| Concepto | Bajo | Realista | Alto |
| --- | ---: | ---: | ---: |
| Dominio | US$10 | US$20 | US$60 |
| Google Cloud/Gemini testing | US$30 | US$150 | US$500 |
| Hosting/observabilidad | US$0 | US$50 | US$150 |
| Email transaccional | US$0 | US$20 | US$80 |
| Diseño/assets | US$0 | US$50 | US$200 |
| Marketing mínimo | US$0 | US$150 | US$500 |
| Payment fees | Variable | Variable | Variable |
| **Total caja 70 días** | **US$40** | **US$440** | **US$1.490** |

Presupuesto recomendado para no sufrir:

> US$500-1.000 de caja para toda la hackathon, sin contar horas propias.

### Costo Real Si Valorizamos Horas De Desarrollo

Supuesto para MVP serio:

| Rol / actividad | Horas estimadas |
| --- | ---: |
| Product discovery + negocio | 30-60 |
| UX/UI + landing | 40-80 |
| Frontend app | 100-180 |
| Backend/API | 120-220 |
| Agentes Gemini | 100-180 |
| Logs/dashboard/evidencia | 40-80 |
| Deploy/DevOps | 30-60 |
| QA/pilotos/ajustes | 60-120 |
| Video/demo/submission | 30-50 |
| **Total** | **550-1.030 h** |

| Valor hora | Costo equivalente |
| --- | ---: |
| US$20/h | US$11.000-20.600 |
| US$40/h | US$22.000-41.200 |

Esto no significa que tengas que cobrar eso de inmediato. Significa que el pricing debe construir un negocio capaz de recuperar desarrollo en el tiempo.

## 9. Modelo De Precios Recomendado

No partiría con planes demasiado baratos. Para ganar la hackathon necesitamos revenue real, pero también demostrar margen.

| Plan | Precio | Incluye | Costo variable estimado | Margen bruto aprox. |
| --- | ---: | --- | ---: | ---: |
| Free | US$0 | 1 evaluación, 30 entregas, marca de agua | US$0.50-1.50 | Negativo/controlado |
| Teacher Lite | US$12/mes | 3 evaluaciones, 90 entregas | US$2-5 | 55-75% |
| Teacher Pro | US$29/mes | 10 evaluaciones, 300 entregas | US$8-18 | 60-75% |
| Cohort Pro | US$79/mes | 30 evaluaciones, 1.000 entregas | US$25-60 | 55-70% |
| Pilot Pack | US$99 único | 3 evaluaciones reales, hasta 150 entregas, onboarding | US$5-15 + soporte | 50-85% |

El **Pilot Pack de US$99** es el más importante para la hackathon. Es fácil de entender, vendible y genera evidencia rápida:

> Te operamos tus próximas 3 evaluaciones prácticas con IA: diseño, rúbrica, corrección, feedback y reporte.

Para suscripciones, la unidad comercial debe ser:

> entregas corregidas por mes, no "uso ilimitado".

## 10. Costos De Pago

Si usamos Stripe, la tarifa online estándar publicada es **2.9% + US$0.30** por transacción para tarjetas domésticas en EE. UU.; pueden aplicarse recargos por tarjetas internacionales o conversión de moneda.

| Venta | Fee aproximado Stripe | Neto aproximado |
| --- | ---: | ---: |
| US$12 | US$0.65 | US$11.35 |
| US$29 | US$1.14 | US$27.86 |
| US$79 | US$2.59 | US$76.41 |
| US$99 | US$3.17 | US$95.83 |

Para Chile, habría que decidir si usar Stripe con cuenta habilitada, PayPal, MercadoPago, Flow o Transbank.

Para la hackathon, lo más importante es que la evidencia financiera sea clara y exportable en USD.

## 11. Regla De Oro Para No Perder Plata

No vender:

> Correcciones ilimitadas con IA.

Vender:

> Incluye hasta X entregas corregidas por mes. Entregas adicionales: US$0.05-0.15 cada una.

Precio recomendado por sobreuso:

| Tipo de uso extra | Precio sugerido |
| --- | ---: |
| Entrega adicional corregida | US$0.08 |
| Evaluación adicional sin correcciones | US$0.50 |
| Evaluación adicional con hasta 30 entregas | US$3.00 |
| Reporte avanzado adicional | US$1.00 |
| Revisión premium con modelo avanzado | US$0.20-0.50 por entrega |

Esto deja margen incluso si algunos casos escalan a Gemini 3.5 Flash.

## 12. Qué Deberíamos Mostrar En La Postulación

En la app necesitamos un dashboard interno de costos desde el día 1:

| Métrica | Por qué importa |
| --- | --- |
| Tokens input por agente | Control de costo. |
| Tokens output por agente | Control de costo. |
| Modelo usado | Justifica routing. |
| Costo estimado por ejecución | Unit economics. |
| Costo por evaluación | Pricing. |
| Costo por docente | Rentabilidad. |
| Costo por estudiante corregido | Margen. |
| Revenue por cliente | Business viability. |
| Marketing spend | Requisito Devpost. |
| Costos cubiertos por créditos | Transparencia. |
| Costos efectivamente pagados | Evidencia financiera. |

Devpost puede pedir documentación financiera adicional, revenue records, expense statements o prueba de relación con usuarios/clientes, así que esto no debería quedar para el final.

## Recomendación Final

Pricing inicial:

| Oferta | Precio |
| --- | ---: |
| Free | US$0 |
| Teacher Lite | US$12/mes |
| Teacher Pro | US$29/mes |
| Cohort Pro | US$79/mes |
| Pilot Pack hackathon | US$99 pago único |

Política técnica:

> Gemini 3.1 Flash-Lite para volumen, Gemini 3 Flash para generación/reportes, Gemini 3.5 Flash solo para fallback o tareas premium.

Con eso, el negocio puede tener buen margen, el costo de operación es defendible y la historia para la hackathon queda sólida:

> No solo generamos revenue. Sabemos cuánto cuesta cada evaluación, cada corrección y cada agente. GradeOps AI es un negocio medible, no una demo.


---

## Source: `.raw/05-chat.md`

# Herramientas Personales De IA Y Costos Productivos

> Nota raw formateada desde la conversación sobre cómo considerar las suscripciones personales de IA en el costo de GradeOps AI.

> Decisión posterior: este archivo conserva el razonamiento original. La fuente canónica separa `Development tooling` de `Production runtime` en `../cost-model.md`.

## Prompt Original

> Yo pago Google One con plan "Google AI Pro"; además cuento con suscripciones de Claude Code Pro, ChatGPT Plus con Codex y GitHub Copilot Pro porque soy docente. Además trabajo con OpenCode con modelos gratuitos. Todo esto como parte para desarrollo utilizando AI.

## Tesis Principal

Esto cambia el costo de desarrollo, pero no cambia el costo operativo del producto.

Tu stack de IA personal te da una ventaja enorme para construir **GradeOps AI** con bajo gasto inicial, pero para la hackathon hay que separar cuatro bolsas:

| Bolsa | Qué incluye | Afecta pricing SaaS |
| --- | --- | --- |
| Desarrollo asistido por IA | Claude Code, ChatGPT Plus/Codex, Copilot, OpenCode, Gemini/Antigravity. | Parcialmente. |
| Operación del producto | Gemini API, Cloud Run, DB, Storage, logs, emails. | Sí, directo. |
| Marketing/adquisición | Ads, landing, dominios comerciales, campañas, outreach pagado. | Sí, pero separado. |
| Costo hundido/personal | Herramientas que ya pagabas antes y usas para varias cosas. | No debería definir precio. |

Punto clave:

> Tus suscripciones ayudan a construir más rápido, pero no reemplazan la facturación real del producto.

Para producción, **GradeOps AI** debe usar API/Cloud facturable y trazable, no sesiones personales de herramientas de desarrollo.

## 1. Suscripciones Personales: Construcción, No Operación SaaS

Tu stack actual:

| Herramienta | Uso correcto en GradeOps AI | Clasificación |
| --- | --- | --- |
| Google AI Pro | Ideación, prototipos, Gemini en herramientas Google, Antigravity, AI Studio. | Desarrollo/R&D. |
| Claude Code Pro | Implementación, refactor, arquitectura, debugging. | Desarrollo/R&D. |
| ChatGPT Plus + Codex | Diseño funcional, revisión, generación de código, documentación. | Desarrollo/R&D. |
| GitHub Copilot Pro | Autocompletado, generación local, productividad IDE. | Desarrollo/R&D. |
| OpenCode + modelos gratuitos | Tareas de código de bajo costo, asistencia local/CLI. | Desarrollo/R&D. |

Lo importante:

> Ninguna de esas suscripciones debería ser usada como motor productivo de GradeOps AI.

El producto desplegado debe usar APIs/billing trazable:

- Gemini API o Vertex AI para cumplir la hackathon;
- opcionalmente otros proveedores vía API si más adelante conviene.

Notas de referencia:

- OpenAI declara que ChatGPT Plus cuesta US$20/mes y que el uso de API se factura por separado.
- Codex está incluido en planes elegibles de ChatGPT, con límites según plan.
- Anthropic separa sus planes de suscripción de la API/Console.
- Claude Pro cuesta US$20/mes.
- Claude Code puede usarse con planes Pro/Max, pero los usos intensivos o por API tienen otra lógica de consumo.
- GitHub permite Copilot Pro gratis para profesores verificados, con reevaluación mensual de elegibilidad.

## 2. Google AI Pro Ayuda, Pero No Elimina El Costo Productivo

Google AI Pro sirve mucho porque incluye:

- límites ampliados en AI Studio;
- Google Antigravity;
- Jules;
- beneficios del Google Developer Program.

Google One muestra que Google AI Pro incluye **US$10 mensuales en créditos de Google Cloud**, mientras planes superiores muestran montos mayores.

Además, la ayuda oficial de Google indica que Google AI Pro da acceso a:

- Google AI Studio;
- Antigravity con cuotas más altas;
- créditos/beneficios de Google Developer Program.

Las cuotas dependen del producto y disponibilidad.

### Lectura Práctica

Tu Google AI Pro puede bajar el gasto de prototipado y despliegue inicial, pero **GradeOps AI** debe tener su propio:

- proyecto Google Cloud;
- billing;
- logs;
- presupuestos;
- costos medidos.

No debemos decir:

> No tenemos costos porque usamos mi plan Google AI Pro.

Debemos decir:

> Usamos créditos y herramientas personales para acelerar desarrollo, pero el producto mide costos reales por ejecución de agente, tokens, hosting y operación.

Eso suena mucho más serio ante jueces.

## 3. Cómo Reportarlo Para La Hackathon

Criterio contable simple:

### A. Costos Operativos Del Producto

Estos sí van directo a **Total Costs**:

| Concepto | Reportar como |
| --- | --- |
| Gemini API / Vertex AI | AI API usage. |
| Cloud Run | Hosting/backend execution. |
| Firestore/Cloud SQL | Database. |
| Cloud Storage | File storage. |
| Cloud Logging/Monitoring | Observability/logging. |
| Dominio | Product/domain cost. |
| Email transaccional | Product communication. |
| Stripe/PayPal/MercadoPago fees | Payment processing. |
| Contractors, si existen | Contractor fees. |

### B. Suscripciones Personales De IA

Estas no son COGS puro, pero pueden reportarse como **allocated development tooling cost** si se facturaron durante el período y fueron usadas directamente para construir el proyecto.

| Suscripción | Cómo reportarla |
| --- | --- |
| Claude Code Pro | Allocated AI development tooling. |
| ChatGPT Plus/Codex | Allocated AI development tooling. |
| Google AI Pro | Pre-existing AI development tooling + Google Cloud credits. |
| GitHub Copilot Pro docente | Free verified teacher benefit, US$0 cash cost. |
| OpenCode modelos gratuitos | Free/open tooling, US$0 cash cost. |

### Estrategia Transparente

Reportar dos números:

- cash cost;
- allocated cost.

Ejemplo conservador:

> Total Costs: US$244.32. Includes US$184.32 product operating costs and US$60.00 allocated AI development tooling during the hackathon period. Marketing and customer acquisition spend: US$0.

Ejemplo separando tooling preexistente:

> Total Costs: US$184.32 cash cost. Includes Google Cloud/Gemini API usage, Cloud Run hosting, Firestore, domain, and payment fees.

> Additional pre-existing AI development tooling used: Claude Code Pro, ChatGPT Plus/Codex, Google AI Pro, GitHub Copilot Pro teacher benefit and OpenCode. These were used for development acceleration and are not included in product COGS.

Preferencia:

> Usar el enfoque conservador si queremos mostrar máxima rigurosidad. Los jueces valoran que entendamos los costos.

## 4. Efecto En El Costo De Desarrollo

Antes estimé el costo de desarrollo valorizando horas. Con tus suscripciones, la caja real baja mucho.

### Desarrollo Con Tus Herramientas Actuales

| Concepto | Costo incremental mensual probable |
| --- | ---: |
| Claude Code Pro | US$20 si lo asignamos completo |
| ChatGPT Plus/Codex | US$20 si lo asignamos completo |
| GitHub Copilot Pro | US$0 si estás con beneficio docente |
| OpenCode + modelos gratuitos | US$0 |
| Google AI Pro | Usar valor real de tu factura; además considera créditos incluidos |
| Google Cloud/Gemini testing | US$0-100 inicial |
| Dominio | US$10-30 anual aprox. |
| Email/landing/tools | US$0-30 mensual |
| Caja incremental fuerte | Baja |

Tu ventaja real no es solo pagar herramientas. Es que puedes operar como "mini equipo":

| Tarea | Herramienta principal |
| --- | --- |
| Arquitectura, decisiones, documentación | ChatGPT / Claude |
| Implementación fuerte | Claude Code / Codex |
| Autocompletado IDE | GitHub Copilot |
| Experimentación con Gemini | Google AI Pro / AI Studio / Antigravity |
| Bajo costo / alternativas | OpenCode |
| Revisión final y estrategia | ChatGPT + documentación propia |

Esto reduce el costo caja, pero no elimina el costo de horas.

Para la hackathon, lo podemos narrar como:

> The team used AI development tools to compress product development time, while the deployed product runs on Google Cloud and Gemini API with full operational cost tracking.

## 5. Esto No Debe Bajar Demasiado El Precio De Venta

No conviene razonar así:

> Como desarrollo barato con mis suscripciones, puedo cobrar barato.

El precio no debe salir del costo de construir. Debe salir de:

- valor ahorrado al docente;
- costo operativo por evaluación;
- soporte;
- margen;
- recuperación futura del desarrollo;
- percepción profesional del producto.

Tus suscripciones bajan el R&D cash burn, no el costo unitario de cada cliente.

El costo unitario sigue siendo:

```text
Costo por evaluación =
Gemini/API + hosting + storage + logs + emails + soporte + retries + margen de error
```

## 6. Pricing Ajustado Considerando La Ventaja

Mantendría precios en USD para la hackathon, aunque localmente puedas cobrar en CLP.

| Plan | Precio recomendado | Uso incluido | Motivo |
| --- | ---: | --- | --- |
| Free | US$0 | 1 evaluación / 30 entregas | Demo controlada. |
| Teacher Starter | US$12/mes | 3 evaluaciones / 90 entregas | Entrada fácil. |
| Teacher Pro | US$29/mes | 10 evaluaciones / 300 entregas | Plan principal. |
| Cohort Pro | US$79/mes | 30 evaluaciones / 1.000 entregas | Bootcamps/tutores. |
| Pilot Pack | US$49-99 único | 3 evaluaciones reales + reporte | Mejor para hackathon. |

Para Chile/LatAm:

| Plan | Precio CLP sugerido |
| --- | ---: |
| Teacher Starter | $9.990 CLP/mes |
| Teacher Pro | $19.990-$24.990 CLP/mes |
| Cohort Pro | $59.990-$79.990 CLP/mes |
| Pilot Pack | $39.990-$79.990 CLP único |

Para la hackathon, el **Pilot Pack** es el más importante. Necesitamos pagos reales más que MRR perfecto.

## 7. Archivo Recomendado Para El Repo

En `grade-ops-ai-docs`, agregaría:

```text
/business/cost-model.md
```

Estructura recomendada:

```markdown
# GradeOps AI — Cost Model

## 1. Product Operating Costs
- Gemini API / Vertex AI
- Google Cloud Run
- Firestore / Cloud SQL
- Cloud Storage
- Cloud Logging
- Email provider
- Payment processing fees

## 2. AI Development Tooling
The team used pre-existing AI subscriptions and free tools to accelerate development:
- Google AI Pro
- Claude Code Pro
- ChatGPT Plus with Codex
- GitHub Copilot Pro teacher benefit
- OpenCode with free models

These tools were used for software development, documentation, architecture and testing support. They are not part of the runtime product COGS.

## 3. Cost Reporting Method
We separate:
- Cash operating costs
- Allocated development tooling
- Marketing and customer acquisition spend
- Credits and free-tier benefits

## 4. Unit Economics
Primary cost unit:
- Cost per assessment
- Cost per graded submission
- Cost per active teacher
```

## 8. Riesgo Que Debemos Evitar

No mezclar herramientas personales con producción.

### Mala Práctica

> GradeOps AI usa mi sesión de ChatGPT/Claude/Gemini web para corregir entregas.

### Buena Práctica

> GradeOps AI usa Gemini API en backend desplegado, registra cada ejecución de agente, calcula tokens/costo estimado, guarda output estructurado y permite auditoría.

La segunda opción cumple mucho mejor con la hackathon y con un futuro SaaS real.

## 9. Decisión Estratégica

Tu stack actual permite:

| Sin tus herramientas | Con tus herramientas |
| --- | --- |
| Desarrollar lento. | Iterar rápido. |
| Contratar más apoyo. | Automatizar parte del trabajo. |
| Gastar más en prototipado. | Gastar poco en R&D. |
| Depender de una sola IA. | Comparar salidas entre modelos. |
| Menos documentación. | Generar documentación viva. |
| Más riesgo de bloqueo. | Más alternativas. |

Pero para pricing, la regla sigue siendo:

> Cobrar por valor y volumen de uso, no por lo barato que nos salió construir.

## Recomendación Final

Usa tus suscripciones como palanca de desarrollo, no como subsidio del negocio.

Para **GradeOps AI**, dejaría el modelo así:

| Área | Decisión |
| --- | --- |
| Development tooling | Mostly covered by pre-existing personal AI subscriptions. |
| Production runtime | Measured separately using Google Cloud + Gemini API billing. |
| Pricing | Based on assessments, graded submissions, reports and teacher value. |
| Hackathon reporting | Disclose operating costs, marketing spend, revenue, and optionally allocated AI development tooling. |

Principio interno:

> Las suscripciones personales aceleran la construcción; la API productiva demuestra el negocio.


---

## Source: `.raw/06-chat.md`

# Revisión Profunda De Documentación Canónica

> Nota raw formateada desde la conversación sobre revisión integral de `00-project` y generación de documentos modificados.

## Prompt Original

> Le hice una extensión y repaso a la documentación en el repo de acuerdo a las últimas conversaciones. Hazle un repaso tú, revisión profunda y dime qué debería modificar en cada documento y por qué. Haz esa modificación de acuerdo a los archivos que se encuentran en `00-project` en el repo. Te dejo la imagen de la lista completa de los documentos. Aparte de entregarme las modificaciones por el chat, entrégamelas también en un ZIP con los documentos que hayan sido modificados.

## Contexto

Se revisaron los documentos canónicos de `00-project`, contrastándolos con:

- la lectura estratégica previa de la hackathon;
- las reglas actuales de Devpost;
- la decisión canónica de posicionar el proyecto como **GradeOps AI**;
- la separación entre documentos canónicos y `raw/`.

## Diagnóstico General

El repo ya estaba bien alineado:

- `00-project-review.md` declara correctamente que el proyecto canónico es **GradeOps AI**.
- El foco es docentes de programación.
- El MVP debe tener aprobación docente, logs de agentes y costos separados de tooling personal.
- La separación entre archivos canónicos y `raw/` ya estaba clara.
- `raw/` debe conservarse como historial, no como especificación vigente.

La mejora principal fue pasar de:

> Documentos estratégicos correctos.

A:

> Documentos accionables para construir, vender y postular.

Devpost confirma que el reto exige:

- negocio real;
- clientes/revenue reales;
- operación con IA;
- uso de Google Cloud;
- Gemini API en proyectos con LLM;
- evidencia de logs/API/dashboards;
- evidencia de clientes;
- video menor a 3 minutos.

## Cambios Aplicados Por Documento

| Documento | Qué se modificó | Por qué |
| --- | --- | --- |
| `00-project-review.md` | Se convirtió en índice ejecutivo/canónico del proyecto, con decisiones, roles documentales, riesgos críticos, coherencia, validaciones pendientes y próximos documentos sugeridos. | El archivo ya resumía bien el estado del proyecto, pero faltaba que funcionara como puerta de entrada para cualquiera que llegue al repo. |
| `vision.md` | Se agregó North Star, ICP, segmentos iniciales, moat estratégico, resultados por docente/estudiante/negocio y límites explícitos. | La visión estaba correcta, pero muy sintética. Faltaba diferenciar visión de producto de ventaja competitiva. |
| `pitch.md` | Se agregó pitch de 60 segundos, variantes por comprador, objeciones/respuestas, oferta inicial y líneas de apertura/cierre para demo. | El pitch ya decía bien qué es GradeOps AI, pero necesitaba material comercial directo para vender pilotos y grabar video. |
| `problem.md` | Se agregaron Jobs To Be Done, hipótesis de validación, problema económico, límites del problema y riesgos de interpretación. | El problema estaba claro, pero faltaba formularlo como algo testeable con usuarios reales. |
| `solution.md` | Se agregó matriz de alcance MVP, coreografía de agentes, estados de aprobación, modelo mínimo de datos, seguridad/privacidad, NFR y política de confianza. | Era el documento más importante técnicamente. Ya tenía flujo y agentes, pero faltaban contratos mínimos para implementación y demo. |
| `roadmap.md` | Se agregó critical path, weekly execution plan desde el 8 de junio al 17 de agosto, criterios de kill/pivot y Definition of Done para la postulación. | El roadmap estaba bien por fases, pero necesitaba calendario operativo y criterios de salida duros. |
| `hackathon-strategy.md` | Se agregó matriz de criterios de evaluación, inventario de evidencia, guion de demo de 3 minutos y checklist de cumplimiento. | El archivo ya recogía las restricciones principales, pero faltaba mapearlas contra evidencia concreta que se debe capturar durante el desarrollo. |
| `cost-model.md` | Se actualizó el enfoque de costos, se agregaron supuestos actuales de modelos, margen bruto, esquema de ledger de ingresos/costos y separación más fuerte entre runtime y tooling personal. | El documento ya tenía buenos principios de costos y pricing. Se reforzó porque Devpost exige reportar revenue, costos, marketing spend, related-party revenue y evidencia financiera. |

## Documentos No Modificados

No se modificaron:

- `raw/00-chat.md`;
- `raw/01-chat.md`;
- `raw/02-chat.md`;
- `raw/03-chat.md`;
- `raw/04-chat.md`;
- `raw/05-chat.md`.

Motivo:

> Mantenerlos intactos es correcto porque son historial de razonamiento, no la fuente canónica del producto.

El propio repo ya declara esa intención.

## Ajuste Importante En Costos

Se actualizó `cost-model.md` para que no dependa de nombres/precios obsoletos o demasiado específicos.

La política quedó basada en clases de modelo:

- Flash-Lite;
- Flash;
- premium fallback.

La página oficial de Gemini muestra precios actuales para:

- Gemini 3.1 Flash-Lite;
- Gemini 3 Flash Preview;
- Grounding con Google Search;
- límites/costos asociados.

También se dejó recordatorio de verificar Cloud Run y Firestore antes de la postulación final:

- Cloud Run mantiene free tier por vCPU/RAM/requests según modalidad.
- Firestore mantiene free tier diario de lecturas/escrituras/deletes y 1 GiB almacenado para una base gratuita por proyecto.

## Estado De Entrega

No se hizo commit directo sobre `master`.

Los archivos quedaron listos para:

- reemplazar;
- revisar;
- commitear;
- usar como base documental del proyecto.

## Entregable ZIP

Se generó un ZIP con los 8 documentos modificados:

```text
gradeops-ai-00-project-modified-docs.zip
```


---

## Source: `.raw/07-chat.md`

# Alineación De `01-business` Con `00-project`

> Nota raw formateada desde la conversación sobre revisión y actualización de la documentación de negocio.

## Prompt Original

> Ok, listo, lo actualicé en el repo. Ahora deberíamos seguir con la documentación de `01-business` considerando lo ya definido en `00-project`. Hay que revisar lo que hizo Copilot inicialmente cuando se creó el repo y alinear con lo ya visto hasta ahora en las revisiones anteriores.

## Diagnóstico Inicial

Sí: `01-business` estaba demasiado inicial.

Copilot dejó una base correcta, pero muy genérica:

- `business-model.md` solo definía cliente, oferta y revenue en pocas líneas.
- `customer-discovery.md` solo dejaba preguntas base.
- `pricing.md` todavía tenía precios amplios no alineados con el modelo canónico actual.

## Criterios De Alineación

La actualización se alineó con `00-project`, especialmente con estas decisiones:

- proyecto canónico: **GradeOps AI**;
- foco en docentes de programación;
- MVP de evaluaciones prácticas;
- pricing por evaluaciones + entregas corregidas;
- control docente;
- evidencia como output obligatorio;
- separación entre tooling personal y runtime productivo;
- costos, revenue y logs como parte del negocio.

También se cruzó con la lógica oficial de la hackathon:

- negocio real;
- usuarios reales;
- revenue;
- AI agents en producción;
- Google Cloud;
- evidencia de producto;
- gastos;
- logs/API/dashboards;
- evidencia de clientes.

## Cambios Aplicados En `01-business`

| Documento | Problema detectado | Modificación aplicada |
| --- | --- | --- |
| `business-model.md` | Muy genérico; no convertía la idea en modelo vendible. | Se rehízo como modelo de negocio completo: ICP, segmentos, JTBD, propuesta de valor, oferta, revenue streams, unit economics, adquisición, retención, riesgos y gates de validación. |
| `customer-discovery.md` | Tenía preguntas útiles, pero no suficientes para validar venta real. | Se agregaron hipótesis, targets priorizados, screener, entrevista completa, scoring de dolor/intención de compra, evidencia por entrevista, síntesis por batch y reglas de privacidad/consentimiento. |
| `go-to-market.md` | Correcto pero muy superficial; faltaba ejecución concreta. | Se agregó GTM founder-led, Pilot Pack, canales, flujo de venta, mensajes de outreach, landing copy, métricas de funnel, plan semanal, objeciones y referral motion. |
| `hackathon-strategy.md` | Duplicaba de forma débil lo de `00-project`. | Se convirtió en estrategia de evidencia business: revenue, customers, agent evidence, dashboard, demo business arc, narrativa, checklist y riesgos de submission. |
| `pricing.md` | No estaba alineado con `cost-model.md`. | Se alineó con los planes canónicos: Free, Teacher Lite, Teacher Pro, Cohort Pro y Pilot Pack; se agregó CLP, overuse, margen, experimentos de precio, descuentos y reporting. |

## Decisión Importante

El foco de `01-business` debe ser distinto al de `00-project`:

| Carpeta | Pregunta Que Responde |
| --- | --- |
| `00-project` | Qué estamos construyendo y por qué. |
| `01-business` | A quién se vende, cómo se valida, cuánto se cobra, cómo se consigue evidencia y cómo se prueba negocio real. |

## Idioma

Los documentos quedaron en inglés porque sirven directamente para preparar:

- submission;
- narrativa;
- testing evidence;
- demo;
- materiales de evaluación ante la hackathon.

## Entregable ZIP

Se generó un ZIP con los 5 documentos modificados:

```text
gradeops-ai-01-business-modified-docs.zip
```

## Nota Operativa

Durante la revisión se generó por error un archivo vacío `dummy` en el repo y se eliminó inmediatamente.

No quedó archivo residual en el árbol del repo; solo quedarían esos commits mínimos en el historial si la operación fue commiteada.


---

## Source: `.raw/08-chat.md`

# Alineación De `02-product`

> Nota raw formateada desde la conversación sobre revisión y actualización de la documentación de producto.

## Prompt Original

> Ahora toca `02-product`.

## Resultado General

Se revisó `02-product` y se dejó alineado con lo ya consolidado en:

- `00-project`;
- `01-business`.

## Diagnóstico Inicial

Copilot dejó buenos encabezados, pero los documentos todavía estaban en modo "nota inicial".

Ejemplos:

- `mvp-scope.md` definía solo in/out scope en pocas líneas.
- `personas.md` tenía 3 perfiles muy resumidos.
- `user-stories.md` traía 6 historias sin prioridad ni criterios de aceptación.

Para esta etapa, el producto necesitaba quedar mucho más ejecutable.

## Cambios Aplicados En `02-product`

| Documento | Modificación principal |
| --- | --- |
| `mvp-scope.md` | Se convirtió en una especificación de alcance MVP: objetivo, experiencia, matriz Must/Should/Could/Do Not Build, estados del producto, roles, NFR, criterios de aceptación y cut line. |
| `personas.md` | Se ampliaron las personas: Lead Instructor, Tutor, Bootcamp Instructor, Academy Operator, Program Manager, Student, Reviewer y anti-personas. |
| `user-stories.md` | Se estructuró por épicas, prioridades P0/P1/P2/Out y criterios de aceptación. Quedó como backlog base para implementación. |
| `workflows.md` | Pasó de un flujo general a workflows detallados: onboarding, creación de evaluación, rúbrica, submissions, grading, feedback, learning gaps, reportes, logs y evidencia. |
| `metrics.md` | Se rehízo como sistema de métricas de producto, negocio, AI-native operations, confianza docente, unit economics y evidencia de hackathon. |

## Decisión De Enfoque

`02-product` ahora responde a:

> ¿Qué debe hacer exactamente el producto MVP para probar el negocio?

No intenta resolver arquitectura interna todavía. Eso debe quedar en una carpeta técnica posterior.

El foco de esta carpeta queda en:

- producto;
- alcance;
- usuarios;
- historias;
- flujos;
- estados;
- métricas;
- criterios de aceptación.

## Estado De Entrega

No se modificó GitHub directamente.

Los archivos quedaron listos para:

- reemplazar;
- revisar;
- commitear;
- usar como base de implementación del MVP.

## Entregable ZIP

Se generó un ZIP con los documentos modificados:

```text
gradeops-ai-02-product-modified-docs.zip
```


---

## Source: `.raw/09-chat.md`

ahora toca 03-ai-agents
Received app response
Thought for 4m 52s

Listo. Revisé 03-ai-agents y lo dejé alineado con 00-project, 01-business y 02-product.

El diagnóstico: Copilot dejó una base correcta, pero demasiado mínima. agents-overview.md solo definía principios y lista de agentes en 21 líneas , y cada agente tenía apenas rol, inputs, outputs y control humano, por ejemplo Assessment Agent y Grading Agent . Para este nivel del repo, faltaban contratos, límites, handoffs, logs, flags de incertidumbre y criterios de aceptación.

Qué modifiqué en 03-ai-agents
Documento	Modificación principal
agents-overview.md	Lo convertí en la arquitectura funcional de agentes: flujo completo, principios, checkpoints de control humano, input envelope común, agent log schema, uncertainty flags, model routing y cut line MVP.
assessment-agent.md	Agregué contrato de input/output, reglas de comportamiento, quality checks, flags, handoff al Rubric Agent, logging y criterios de aceptación.
rubric-agent.md	Agregué generación + validación de rúbrica, estructura JSON, criterios de calidad, validaciones, flags y versionado implícito para grading.
grading-agent.md	Reforcé que solo produce sugerencias, no notas finales. Agregué output por criterio, evidencia, uncertainty flags, manejo prudente de integridad académica y control docente.
feedback-agent.md	Agregué contrato de feedback, modos de tono, restricciones de lenguaje student-facing, flags y handoff al Learning Gap Agent.
learning-gap-agent.md	Agregué agregación de brechas, severidad, referencias por criterio/submission, límites contra profiling y handoff al Recovery Agent.
recovery-agent.md	Agregué actividades remediales acotadas, formatos, success criteria, flags y aprobación docente obligatoria.
teacher-report-agent.md	Agregué report modes, estructura de reporte, resumen de evidencia/costo, validación docente y handoff al Ops Agent.
ops-agent.md	Lo reforcé como pieza clave de evidencia: agent logs, workflow evidence, business evidence, cost evidence, missing evidence detection, privacidad y readiness para demo/submission.
Decisión de enfoque

03-ai-agents ahora responde a:

¿Qué hace cada agente, qué recibe, qué devuelve, qué no puede hacer, cómo se audita y dónde vuelve el control al docente?

Esto evita que los agentes queden como “prompts sueltos”. Ahora son contratos operativos para implementación y demo.

No modifiqué GitHub directamente; dejé los archivos listos para reemplazar.

Descarga el ZIP aquí:

Descargar gradeops-ai-03-ai-agents-modified-docs.zip

---

## Source: `.raw/README.md`

# Raw Conversation Notes

This folder stores formatted source conversations and reasoning history for GradeOps AI.

It answers:

> Where did the current project decisions come from, and what reasoning led to the canonical docs?

## Essence

`.raw` is historical context, not the canonical product specification.

The files in this folder preserve:

- early strategic exploration;
- naming decisions;
- hackathon interpretation;
- technical reasoning;
- cost and pricing analysis;
- documentation review summaries;
- folder-by-folder alignment notes.

Use these notes to understand how decisions evolved. Do not treat them as the current source of truth when they conflict with the thematic folders.

## Canonical Sources

Prefer the thematic folders for current decisions:

| Topic | Canonical Folder |
| --- | --- |
| Project strategy | `../00-project/` |
| Business model and GTM | `../01-business/` |
| Product scope and workflows | `../02-product/` |
| Agent contracts | `../03-ai-agents/` |
| Architecture | `../04-architecture/` |
| Evidence | `../05-evidence/` |
| Durable decisions | `../99-decisions/` |

## File Index

| File | Essence |
| --- | --- |
| `00-chat.md` | First strategic reading of the hackathon and the initial ClassOps/assessment-ops framing. |
| `01-chat.md` | Pivot from broad GRADE framing to GradeOps AI as the hackathon positioning. |
| `02-chat.md` | Strategic reading of the TodoDeIA Gemini/XPRIZE article. |
| `03-chat.md` | Technical reading of Gemini, agents, tools, structured outputs, ADK, and Cloud Run. |
| `04-chat.md` | Cost, credits, pricing, unit economics, and operating-budget exploration. |
| `05-chat.md` | Personal AI development tooling versus production runtime costs. |
| `06-chat.md` | Review summary for canonical `00-project` documentation. |
| `07-chat.md` | Review summary for aligning `01-business` with `00-project`. |
| `08-chat.md` | Review summary for aligning `02-product` with project and business docs. |
| `09-chat.md` | Review summary for aligning `03-ai-agents` with project/product docs. |

## How To Use This Folder

Use `.raw` when you need to:

- trace why a decision was made;
- recover earlier alternatives;
- compare old naming or pricing assumptions;
- understand the reasoning behind canonical docs;
- audit whether later docs drifted from the original strategy.

## What Does Not Belong Here

- Current product specifications.
- Final business strategy.
- Implementation contracts.
- Architecture decisions that should be durable.
- Evidence records.
- Customer data.

Move durable decisions to `../99-decisions/`. Move canonical specs to the matching thematic folder.

## Conflict Rule

If `.raw` conflicts with a thematic document, prefer the thematic document.

If `.raw` reveals a stronger or newer decision, promote that decision into the correct thematic folder or a decision record in `../99-decisions/`.

## Formatting Rule

Raw notes should still be readable:

- use professional Markdown;
- keep the original prompt when useful;
- separate diagnosis, decisions, changes, and outcomes;
- use Mermaid for diagrams by default, PlantUML only when needed, and ASCII only as a last fallback.

