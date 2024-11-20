<!-- ![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png) -->

<!-- # Módulo 3: Prompt Engineering y Automatización con Copilot -->

# LAB | Prompt Engineering y Automatización con Copilot

## Introducción

Este laboratorio explora las capacidades avanzadas de Prompt Engineering en Copilot, aprovechando sus características de búsqueda con Bing e integración de imágenes.  Aprenderemos a construir prompts efectivos para tareas de digitalización, reconocimiento de documentos y automatización de procesos con IA.

Accede a Copilot vía esta [URL](https://copilot.cloud.microsoft). Si estás logeado en Office 365, busca la [app de Copilot](https://copilot.cloud.microsoft/chat?fromcode=cmc&redirectid=F3E8B6E4CD4A1E5E5B&auth=2).


## Ejercicio 1: Prompt Engineering Avanzado (45 mins)

**Objetivo:** Practicar la construcción de prompts complejos y específicos para obtener resultados precisos y relevantes en tareas relacionadas con la digitalización y automatización.

Para realizar las prácticas busca los documentos a utilizar por Internet. A posterior, consulta al departamento correspondiente la viabilidad de subir archivos relacionados con Acciona

### Tarea 1: Extracción de Datos de Facturas (Imagen)

**Instrucción:** Sube una imagen de una factura y pide a Copilot que extraiga los siguientes datos en formato JSON:  Número de factura, fecha, nombre del cliente, total a pagar, y desglose de los productos/servicios (incluyendo cantidad, descripción y precio unitario).

**Trabajad vuestro prompt antes de mirar el ejemplo**
```
Analiza la imagen adjunta de una factura y extrae los siguientes datos en formato JSON: número de factura, fecha, nombre del cliente, total a pagar, y un array con el desglose de productos/servicios (cantidad, descripción, precio unitario). Si algún dato no está disponible, indica "N/A" en el valor correspondiente.
```

### Tarea 2:  Generación de Código para Automatización (Archivo + Prompt)

[Ejemplo de csv](https://github.com/araj2/customer-database/blob/master/Ecommerce%20Customers.csv)

**Instrucción:** Sube un archivo CSV con datos de clientes y pide a Copilot que genere un script en Python que automatice el envío de correos electrónicos personalizados a cada cliente, utilizando los datos del CSV.  El correo debe incluir un saludo personalizado, el número de cliente, y un enlace a un portal web.

**Trabajad vuestro prompt antes de mirar el ejemplo**
```
Genera un script en Python que lea el archivo CSV adjunto ("datos_clientes.csv") y envíe un correo electrónico personalizado a cada cliente. El correo debe contener:

* Asunto: "Bienvenido a nuestro portal, [Nombre del Cliente]"
* Cuerpo: "Estimado/a [Nombre del Cliente], gracias por registrarte. Tu número de cliente es [Número de Cliente]. Accede a nuestro portal: [enlace_portal]"
Reemplaza "[enlace_portal]" con "https://miportal.com".  Utiliza la librería `smtplib` para el envío de correos.  Asume que las credenciales del servidor SMTP están almacenadas en variables de entorno.
```

### Tarea 3:  Generación de un Informe Técnico a partir de Especificaciones (PDF)

Descarga el siguiente [PDF](https://www.daikin.eu/content/dam/document-library/declaration-of-conformity/ac/split/2amx-g/MXS-H_AMX-G_3PES401524-1_IM_Declaration%20of%20Conformity_Spanish.pdf)

**Instrucción:** Sube un PDF con las especificaciones técnicas de un equipo  (como el adjunto) y pide a Copilot que genere un informe técnico resumido que incluya:

 - Características principales:
 - Instrucciones de instalación: 
 - Tabla de resolución de problemas:
 - Información adicional relevante: 

El informe debe estar en formato Markdown, con tablas y listas donde sea apropiado.  Especifica que se omitan detalles excesivamente técnicos o redundantes, enfocándose en la información esencial para un instalador.

**Trabajad vuestro prompt antes de mirar el ejemplo**
```
Genera un informe técnico resumido en formato Markdown a partir del PDF adjunto ("manual_instalacion_aire_acondicionado.pdf").  El informe debe estar dirigido a instaladores y debe incluir:

*Características principales: Modelo, tipo de refrigerante, capacidad de enfriamiento, voltaje, dimensiones, peso.
*Instrucciones de instalación clave: Pasos críticos de la instalación, precauciones de seguridad importantes, herramientas especiales necesarias.
*Tabla de resolución de problemas: Describe los problemas más comunes que pueden surgir durante la instalación, sus posibles causas y las soluciones recomendadas.
*Información adicional relevante:  Información de garantía, certificaciones (si las hay), y datos de contacto del fabricante.

Omite detalles excesivamente técnicos o redundantes.  Enfocate en la información esencial para una instalación correcta y segura.  Utiliza tablas y listas para organizar la información de forma clara.
```

## Ejercicio 2:  Aplicaciones avanzadas (30 mins)

**Objetivo:** Explorar cómo Copilot puede asistir en tareas diarias de digitalización y automatización.

Realiza las siguientes tareas utilizando Copilot:

## Tres tareas avanzadas para Copilot:

### 1. Análisis de Sentimiento y Resumen de Actas de Reunión:

**Descripción:** Imagina que tienes las actas de una reunión en formato texto. Copilot debe:

* **Identificar a los participantes** de la reunión y crear una lista.
* **Analizar el sentimiento** de cada intervención o párrafo, clasificándolo como positivo, negativo o neutral. 
* **Generar un resumen conciso** de la reunión, destacando los puntos clave, decisiones tomadas y próximos pasos. 

**Ejemplo de input:**  ([Acta aleatoria de ayuntamiento](https://www.ayto-sotodelreal.es/wp-content/uploads/2016/04/ACTA-DE-REUNION-DEL-CONSEJO-SECTORIAL-DE-URBANIZACIONES-01-07-16.pdf))

**Ejemplo de output deseado:**

* **Participantes:** [Persona 1, Persona 2, Persona 3]
* **Análisis de Sentimiento:**
    * Párrafo 1 (Persona 1): Positivo
    * Párrafo 2 (Persona 2): Negativo 
    * ...
* **Resumen:** Se discutió el Proyecto X.  Persona 1 se mostró optimista sobre el progreso.  Persona 2 expresó preocupaciones sobre el presupuesto. Se decidió...  Próximos pasos: ...

**Beneficios:** Automatiza el análisis de reuniones, identifica rápidamente puntos de conflicto y facilita la toma de decisiones.

**Trabajad vuestro prompt antes de mirar el ejemplo**
```
Actúa como un analista de reuniones. Te proporciono la transcripcion de una reunión y necesito que:

1. Identifiques a todos los participantes mencionados en el texto.
2. Analices el sentimiento general de cada intervención o párrafo, clasificándolo como positivo, negativo o neutral. 
3. Generes un resumen conciso de la reunión, destacando los puntos clave, decisiones tomadas y próximos pasos. 
```


### 2.  Creación de un Chatbot de Soporte Técnico Personalizado: 

**Descripción:**  Define un producto o servicio ficticio (ej. una app para gestionar tareas). Copilot debe:

*  **Generar un conjunto de preguntas frecuentes** (FAQs) típicas que los usuarios tendrían sobre el producto.
* **Crear un script de chatbot** capaz de responder a esas preguntas, con diferentes opciones de respuesta y  teniendo en cuenta el contexto de la conversación.

**Ejemplo de input:**

* **Nombre del producto:** TaskMaster - App para organizar tareas y proyectos.
* **Descripción:** Permite crear listas de tareas, asignar responsables, establecer fechas límite, etc.

**Ejemplo de output deseado:**

* **FAQs:**
    * ¿Cómo creo una nueva tarea?
    * ¿Puedo compartir proyectos con otros usuarios?
    * ...
* **Script de chatbot:**
    * Usuario:  "Hola, ¿cómo puedo agregar una tarea?"
    * Chatbot: "¡Hola! Para agregar una tarea, haz clic en el botón '+', luego..." 

**Beneficios:** Crea rápidamente un chatbot funcional para tu producto, mejorando la atención al cliente y liberando recursos.

**Trabajad vuestro prompt antes de mirar el ejemplo**
´´´
Necesito tu ayuda para crear un chatbot de soporte técnico para mi nuevo producto.  
Información del producto:

* Nombre: Afectación de aerogeneradores en aves
* Descripción: evitar accidentes ahuyentando al animal con luces y chorros desde las palas
Tareas:
1. Genera una lista de 5 a 10 preguntas frecuentes (FAQs)  que los usuarios podrían tener sobre este producto.
2. Crea un script básico para un chatbot que pueda responder a esas preguntas.  El chatbot debe ser amigable, brindar respuestas claras y concisas, y ofrecer opciones adicionales si el usuario necesita más información.  

No es necesario que el código del chatbot sea funcional, solo necesito un ejemplo de cómo sería la interacción del usuario con el chatbot.
'''

### 3.  Conversión de Ideas de Negocio en Planes de Marketing:

**Descripción:** Describe una idea de negocio innovadora.  Copilot debe:

* **Identificar el público objetivo** (target) de tu negocio. 
* **Proponer estrategias de marketing digital**  para llegar a ese público (redes sociales, SEO, publicidad online, etc.).
* **Crear un calendario de acciones de marketing**, incluyendo ejemplos de publicaciones, anuncios o contenido. 

**Ejemplo de input:** 

* **Idea de negocio:** Plataforma online que conecta a artistas locales con personas que buscan experiencias culturales únicas (clases de pintura, conciertos privados, etc.). 

**Ejemplo de output deseado:**

* **Público objetivo:**  Personas interesadas en arte y cultura, edades 25-45 años, con ingresos medios-altos, que buscan experiencias auténticas.
* **Estrategias de marketing:**
    * **Redes Sociales:** Creación de perfiles atractivos en Instagram y Facebook,  publicación de contenido visual de alta calidad (fotos, videos), organización de concursos y sorteos.
    * **SEO:** Optimizar el sitio web con palabras clave relevantes (ej. "Clases de arte", "Conciertos privados").
    * ...
* **Calendario:**
    * **Semana 1:** Publicar en Instagram 3 veces al día.  Crear anuncio en Facebook con un 10% de descuento...

**Beneficios:** Te ayuda a planificar tu estrategia de marketing, definir tu público y lanzar tu idea de negocio de forma efectiva.

**Trabajad vuestro prompt antes de mirar el ejemplo**
```
Imagina que soy un emprendedor y necesito ayuda para elaborar un plan de marketing digital para mi nueva idea de negocio. 
Idea de negocio:
ahuyentar aves con el chorro de las palas de los aerogeneradores
Tareas:
1.  Identifica y describe al público objetivo (target) ideal para esta idea de negocio. 
2. Propón al menos 3 estrategias de marketing digital efectivas para llegar a ese público objetivo.  Sé específico y describe cómo se implementaría cada estrategia. 
3. Crea un calendario de acciones de marketing para las próximas 4 semanas, detallando las actividades a realizar en cada canal y proporcionando ejemplos concretos de contenido (ej. ejemplos de publicaciones en redes sociales, anuncios, etc.).
```
## Entrega del proyecto

Comparte una captura de pantalla del chat de Copilot mostrando los resultados de las tareas realizadas.  Incluye una breve reflexión sobre la efectividad de los prompts utilizados y las posibles mejoras.
