# Langflow paso a paso

Ejemplos de Langflow de la asignatura *Búsqueda y gestión de la información y recursos
multimedia* (100009), Universidad de Alcalá, curso 2026/2027.

Son flujos pequeños, ordenados de menos a más, con las piezas que se usan en el Trabajo
de la asignatura. Cada ejemplo es un fichero `.json` que se importa en Langflow y lleva
dentro sus explicaciones, en notas sobre el lienzo: qué hace cada caja y qué probar.

## Qué necesitas

- **Langflow Desktop.** Los ejemplos están hechos con la versión 1.12.2.
- **Un modelo.** Los ejemplos usan **LM Studio** con su servidor local, pero sirve
  cualquier otro proveedor: Ollama, Groq, OpenAI…
- **Desde el ejemplo 9, un modelo de embeddings** en LM Studio, como
  *nomic-embed-text-v1.5*.
- **Desde el ejemplo 11, un modelo que sepa llamar a herramientas.** En LM Studio
  llevan el icono de un martillo (*tool use*). Los ejemplos se han probado con
  **Gemma 4 E4B**.
- **Contexto suficiente.** Los documentos y lo que devuelven las herramientas ocupan
  contexto. Si LM Studio da un error de contexto (*exceeds the available context
  size*), vuelve a cargar el modelo con más **longitud de contexto**, por ejemplo
  16.384.

## Cómo abrir un ejemplo

1. Descarga el `.json` del ejemplo. En GitHub, ábrelo y pulsa *Download raw file*.
2. En **LM Studio**, carga un modelo y arranca el servidor local en la pestaña
   *Developer*.
3. En **Langflow**, desde la pantalla de proyectos, arrastra el `.json` a la ventana o
   usa el botón de subir un flujo.
4. En la caja **LM Studio**, pulsa el botón de recargar de *Model Name* y elige el
   modelo.
5. Abre el **Playground** y sigue la nota *Pruébalo* del lienzo.

**Si usas otro proveedor**, borra la caja LM Studio y pon la tuya. Tiene las mismas
salidas, así que se conecta igual.

## Los ejemplos

### Nivel 1. Lo básico

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 1 | [Hola, flujo](flujos/01-hola-flujo.json) | Un bibliotecario con un rol fijo | Chat Input, Prompt Template, LM Studio, Chat Output |
| 2 | [Plantilla con huecos](flujos/02-plantilla-con-huecos.json) | Explica un tema a una audiencia en un formato | Variables en la plantilla, *System Message* |
| 3 | [Extraer datos](flujos/03-extraer-datos.json) | De una convocatoria a un JSON con título, plazo, destinatarios y requisitos | Structured Output |

### Nivel 2. Combinar piezas

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 4 | [Redactor y revisor](flujos/04-redactor-y-revisor.json) | Un modelo resume; otro señala lo que el original no respalda | Dos modelos en cadena |
| 5 | [Recordar](flujos/05-recordar.json) | Un chat que recuerda la conversación | Message History |
| 6 | [Pedir o imponer](flujos/06-pedir-o-imponer.json) | Una regla fija para los mensajes con un DNI y un modelo que clasifica las consultas | If-Else, Smart Router |

### Nivel 3. Traer información

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 7 | [Un documento entero](flujos/07-un-documento-entero.json) | Responde con un documento completo dentro del prompt | Read File |
| 8 | [La web y las API](flujos/08-la-web-y-las-api.json) | Busca publicaciones en OpenAlex y las presenta en una lista | Dynamic Create Data, API Request, Parser |
| 9 | [Pregunta a tus documentos](flujos/09-pregunta-a-tus-documentos.json) | RAG sobre varias normativas de la UAH | Split Text, LM Studio Embeddings, Chroma DB |
| 10 | [El RAG por dentro](flujos/10-el-rag-por-dentro.json) | El mismo RAG, con los fragmentos recuperados a la vista | Ajustes de troceado y de *k* |

### Nivel 4. Herramientas y agentes

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 11 | [Una herramienta](flujos/11-una-herramienta.json) | Un agente con una calculadora | Agent, Calculator, Tool Mode |
| 12 | [Elegir entre varias](flujos/12-elegir-entre-varias.json) | Busca, lee una web, consulta la Wikipedia, la fecha o calcula | Web Search, URL, Wikipedia, Current Date |
| 13 | [Tu RAG como herramienta](flujos/13-tu-rag-como-herramienta.json) | El agente decide si busca en tus documentos, en la web o en ninguno | Chroma DB como herramienta |
| 14 | [Herramientas que actúan](flujos/14-herramientas-que-actuan.json) | Guarda un informe en un fichero solo cuando una persona escribe GUARDAR | Write File, If-Else como aprobación |
| 15 | [Herramientas de otros](flujos/15-herramientas-de-otros.json) | Usa las herramientas del servidor MCP público de CoinGecko | MCP Tools |
| 16 | [Varios agentes](flujos/16-varios-agentes.json) | Un coordinador encarga a un agente que busque y a otro que escriba | Agent como herramienta |

### Nivel 5. Probar y proteger

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 17 | [Tu batería de pruebas](flujos/17-tu-bateria-de-pruebas.json) | Diez preguntas con su respuesta esperada, de golpe, y un modelo que las corrige | Batch Run |
| 18 | [Defensa en profundidad](flujos/18-defensa-en-profundidad.json) | El RAG con cuatro capas de protección frente a un documento trampa | Guardrails |

## Datos de los ejemplos

En [`datos/`](datos/) están los ficheros que usan algunos ejemplos:

- [`preguntas-permanencia.csv`](datos/preguntas-permanencia.csv): diez preguntas sobre la
  Normativa de permanencia de la UAH, con su respuesta esperada (ejemplo 17).
- [`aviso-biblioteca.md`](datos/aviso-biblioteca.md): un aviso con una instrucción
  escondida para el asistente, un documento trampa (ejemplo 18).

Las normativas de la UAH no están en el repositorio: cada ejemplo enlaza a la web de la
universidad para descargarlas.

## Licencia

Material de Miguel-Ángel Sicilia (Universidad de Alcalá), publicado con licencia
[Creative Commons Reconocimiento 4.0 Internacional (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.es):
puedes reutilizarlo y adaptarlo citando la autoría.
