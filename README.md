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
| 4 | Redactor y revisor | Un modelo resume; otro señala lo que el original no respalda | Dos modelos en cadena |
| 5 | Recordar | Un chat que recuerda la conversación | Message History |
| 6 | Pedir o imponer | Clasifica la pregunta y responde distinto según el tipo | Smart Router, If-Else |

### Nivel 3. Conocimiento

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 7a | Pregunta a tu documento | RAG en pocas cajas | Knowledge |
| 7b | El RAG por dentro | El mismo RAG, pieza a pieza | Read File, Split Text, Embeddings, Chroma DB |

### Nivel 4. Herramientas y agentes

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 8 | Una herramienta | Un agente con una calculadora | Agent, Calculator |
| 9 | Elegir entre varias | Busca, lee una web, consulta la fecha o calcula | Web Search, URL, Wikipedia, Current Date |
| 10 | Tu RAG como herramienta | El agente decide si busca en tus documentos, en la web o en ninguno | Knowledge o Chroma DB como herramienta |
| 11 | Herramientas que actúan | Guarda un informe en un fichero solo si una persona lo aprueba | Write File, Human Input |
| 12 | Herramientas de otros | Usa las herramientas de un servidor MCP público | MCP Tools |
| 13 | Varios agentes | Un coordinador encarga a un agente que busque y a otro que escriba | Agent como herramienta |

### Nivel 5. Fiable y entregable

| # | Ejemplo | Qué hace | Piezas nuevas |
|---|---|---|---|
| 14 | Defensa en profundidad | El RAG protegido contra instrucciones ocultas, con una batería de pruebas | Guardrails, Batch Run |

Los ejemplos sin enlace se irán publicando a lo largo del curso.

## Licencia

Material de Miguel-Ángel Sicilia (Universidad de Alcalá), publicado con licencia
[Creative Commons Reconocimiento 4.0 Internacional (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.es):
puedes reutilizarlo y adaptarlo citando la autoría.
