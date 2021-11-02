# Semana-3
Resumen
# Elegir el mejor servicio de Azure IoT para su aplicación
# Identificación de las opciones de producto
IoT permite a los dispositivos recopilar y luego retransmitir información para el análisis de datos. Los dispositivos inteligentes están equipados con sensores que recopilan datos. Algunos sensores comunes que miden los atributos del mundo físico incluyen:

- Sensores de entorno que capturan los niveles de temperatura y humedad.
- Escáneres de códigos de barras, códigos QR o reconocimiento óptico de caracteres (OCR).
- Sensores de proximidad y ubicación geográfica.
- Sensores de luz, color e infrarrojos.
- Sensores de sonido y ultrasonido.
- Sensores táctiles y de movimiento.
- Sensores de inclinación y acelerómetros.
- Sensores de humo, gas y alcohol.
- Detectores de errores para determinar cuándo hay un problema con el dispositivo.
- Sensores mecánicos que detectan anomalías o deformaciones.
- Sensores de flujo, nivel y presión para medir gases y líquidos.

Con los servicios de Azure IoT, los dispositivos que están equipados con estos tipos de sensores y que pueden conectarse a Internet podrían enviar las lecturas de sus sensores a un punto de conexión específico de Azure por medio de un mensaje. 
Supongamos que su empresa fabrica y opera las máquinas expendedoras refrigeradas inteligentes. ¿Qué tipos de información desearía supervisar? Es posible que quiera asegurarse de que:

- Cada máquina funciona sin errores.
- Las máquinas no se han puesto en peligro.
- Los sistemas de refrigeración de las máquinas mantienen su contenido dentro de un determinado intervalo de temperatura.
- Se le avise cuando los productos alcancen un determinado nivel de inventario para poder reabastecer las máquinas.

Los datos recopilados de estos dispositivos se pueden combinar con servicios de inteligencia artificial de Azure para ayudar a predecir:

- Cuándo necesitan las máquinas mantenimiento proactivo.
- Cuándo va a ser necesario reponer los inventarios y pedir nuevos productos a los proveedores.
- Muchos servicios pueden ayudar e impulsar soluciones de un extremo a otro para IoT en Azure.

# Azure IoT Hub
Azure IoT Hub es un servicio administrado hospedado en la nube que actúa como centro de mensajes centralizado para la comunicación bidireccional entre la aplicación de IoT y los dispositivos que administra. Puede usar Azure IoT Hub para compilar soluciones de IoT con comunicaciones confiables y seguras entre millones de dispositivos de IoT y un back-end de soluciones hospedadas en la nube. Puede conectar prácticamente cualquier dispositivo al centro de IoT.

El servicio IoT Hub admite las comunicaciones desde el dispositivo a la nube y desde la nube al dispositivo. También admite varios patrones de mensajería, como telemetría de dispositivo a la nube, carga de archivos desde dispositivos y métodos de solicitud-respuesta para controlar los dispositivos desde la nube. Una vez que un centro de IoT recibe los mensajes de un dispositivo, puede enrutarlos a otros servicios de Azure.

Desde una perspectiva de nube a dispositivo, IoT Hub permite ordenar y controlar. Es decir, puede tener control remoto manual o automatizado de los dispositivos conectados, por lo que puede indicar al dispositivo que abra válvulas, establezca temperaturas objetivo, reinicie dispositivos atascados, etc.

La supervisión de IoT Hub le ayuda a conservar el estado de la solución, ya que realiza el seguimiento de eventos, como la creación, los errores y las conexiones de dispositivos.

# Azure IoT Central
Azure IoT Central se basa en IoT Hub y agrega un panel que le permite conectar, supervisar y administrar sus dispositivos de IoT. La interfaz de usuario (UI) visual facilita la conexión rápida de nuevos dispositivos y la inspección a medida que comienzan a enviar mensajes de telemetría o de error. Puede ver el rendimiento general de todos los dispositivos en conjunto y configurar alertas que envían notificaciones cuando un dispositivo concreto necesita mantenimiento. Por último, puede enviar actualizaciones de firmware al dispositivo.

Para ayudarle a ponerse en marcha rápidamente, IoT Central proporciona plantillas de inicio para escenarios comunes en diferentes sectores, como la venta directa, la energía, la atención sanitaria y la administración pública. A continuación, puede personalizar las plantillas de inicio directamente en la interfaz de usuario eligiendo los temas existentes o creando su propio tema personalizado, estableciendo el logotipo, etc. IoT Central permite adaptar las plantillas de inicio a los datos específicos que se envían desde los dispositivos, los informes que se quieren ver y las alertas que se quieren enviar.
Puede usar la interfaz de usuario para controlar los dispositivos de forma remota. Esta característica permite enviar una actualización de software o modificar una propiedad del dispositivo. Puede ajustar la temperatura deseada de una o todas las máquinas expendedoras refrigeradas directamente desde dentro de IoT Central.

Una parte clave de IoT Central es el uso de las plantillas de dispositivo. Las plantillas de dispositivo permiten conectar un dispositivo sin programación en el lado del servicio. IoT Central usa las plantillas para construir los paneles, las alertas, etc. Los desarrolladores de dispositivos siguen teniendo que crear código para que se ejecute en los dispositivos, y ese código debe coincidir con la especificación de la plantilla de dispositivo.

# Azure Sphere
Azure Sphere crea una solución de IoT de un extremo a otro de alta seguridad para los clientes que lo abarca todo, desde el hardware y el sistema operativo del dispositivo hasta el método seguro para enviar mensajes desde el dispositivo al centro de mensajes. Azure Sphere tiene características de comunicación y seguridad integradas para dispositivos conectados a Internet.

Azure Sphere consta de tres partes:

- La primera parte es la unidad de microcontrolador (MCU) de Azure Sphere, que se encarga de procesar el sistema operativo y las señales de los sensores conectados. En la siguiente imagen se muestra la MCU del kit de desarrollo Seeed Azure Sphere MT3620, uno de los distintos kits de inicio disponibles para la creación de prototipos y el desarrollo de aplicaciones de Azure Sphere.
- La segunda parte es un sistema operativo (SO) Linux personalizado, que controla la comunicación con el servicio de seguridad y puede ejecutar el software del proveedor.

- La tercera parte es el servicio de seguridad de Azure Sphere, también conocido como AS3. Su trabajo es asegurarse de que el dispositivo no se ha puesto en peligro de forma malintencionada. Cuando el dispositivo intenta conectarse a Azure, primero debe autenticarse, por dispositivo, mediante autenticación basada en certificado. Si se autentica correctamente, AS3 comprueba que el dispositivo no se haya alterado. Una vez que ha establecido un canal de comunicación seguro, AS3 inserta en el dispositivo las actualizaciones de software del sistema operativo o desarrolladas por el cliente (y aprobadas).

# Análisis de los criterios de decisión

En esta unidad se van a analizar los criterios que emplean los expertos para decidir qué servicio de IoT usar para una determinada necesidad empresarial. Comprender estos criterios también puede ayudar a entender mejor las diferencias de cada producto.
# ¿Es fundamental asegurarse de que el dispositivo no esté en peligro?
No en todos los casos. Los fabricantes y los clientes preferirían que sus dispositivos no se pongan en riesgo de forma malintencionada y se utilicen con fines deplorables, si bien en algunos casos es mucho más importante garantizar la integridad. Un ejemplo sería el de un cajero automático en comparación con una lavadora. Cuando la seguridad es una cuestión fundamental en el diseño del producto, la mejor opción de producto es Azure Sphere, que proporciona una solución completa de un extremo a otro para dispositivos de IoT.

Como ya se ha comentado en la unidad anterior, Azure Sphere garantiza un canal seguro de comunicación entre el dispositivo y Azure mediante el control de todo, desde el hardware hasta el sistema operativo y el proceso de autenticación. Esto garantiza que la integridad del dispositivo no esté en peligro. Una vez que se ha establecido un canal seguro, se pueden recibir mensajes del dispositivo de forma segura y se pueden enviar mensajes o actualizaciones de software a este de forma remota.

# ¿Necesito un panel para la generación de informes y la administración?
La siguiente decisión es el nivel de servicios que necesita de la solución de IoT. Si solo quiere conectarse a los dispositivos remotos para recibir telemetría y, ocasionalmente, insertar actualizaciones, pero no necesita ninguna capacidad de elaboración de informes, es posible que prefiera implementar Azure IoT Hub por sí solo. Los programadores siguen pudiendo crear un conjunto personalizado de herramientas de administración e informes mediante la API RESTful de IoT Hub.

Pero si quiere una interfaz de usuario personalizable precompilada con la que ver y controlar los dispositivos de forma remota, puede que prefiera empezar con IoT Central. Con esta solución puede controlar un único dispositivo o todos los dispositivos a la vez, y puede configurar alertas para determinadas condiciones, como un error de dispositivo.

IoT Central se integra con muchos productos de Azure diferentes, como IoT Hub, para crear un panel con características de informes y administración. El panel se basa en plantillas de inicio para escenarios comunes de uso y de la industria. Puede usar el panel generado por la plantilla de inicio tal cual o personalizarlo para que se ajuste a sus necesidades. Puede tener varios paneles y destinarlos a una serie de usuarios.

# Uso de IoT Hub
El equipo directivo senior de Tailwind Traders ha decidido asociarse con un fabricante de electrodomésticos líder para crear una avanzada marca exclusiva que promete un acuerdo de servicio de mantenimiento preventivo. Esta característica única diferenciaría los electrodomésticos de Tailwind Traders en un mercado muy competitivo. La característica también hace que la marca sea lucrativa, ya que sería necesaria una suscripción anual. Para crear una sólida reputación de marca, los electrodomésticos van a enviar información de telemetría a una ubicación centralizada donde se puede analizar y donde se puede programar el mantenimiento.

Los dispositivos no requerirán el control remoto. Simplemente enviarán sus datos de telemetría para el análisis y el mantenimiento proactivo.

Puesto que Tailwind Traders ya dispone de software para administrar las solicitudes de mantenimiento de electrodomésticos, la empresa quiere integrar toda la funcionalidad en este sistema existente.
# ¿Qué servicio debe elegir?
Vamos a aplicar los criterios de decisión de la unidad anterior.

En primer lugar, ¿es fundamental asegurarse de que el dispositivo o, en este caso, cada electrodoméstico, no esté en peligro? Es preferible, aunque no vital, que los dispositivos no estén en peligro. Lo peor que podría suceder es que un pirata informático leyera la temperatura actual de la nevera del cliente o el número de ciclos de lavado que ha completado la lavadora.

Incluso si el cliente llama y notifica un comportamiento extraño con el dispositivo, un técnico podría restablecer o reemplazar el microcontrolador. Podría no justificar el gasto adicional o los recursos de ingeniería que se necesitarían para usar Azure Sphere.

Segundo criterio de decisión: ¿necesito un panel para la generación de informes y la administración? En este caso, no. Tailwind Traders quiere integrar los datos de telemetría y todas las demás funcionalidades en un sistema de solicitud de mantenimiento existente. En este caso, Azure IoT Central no es necesario.

Por lo tanto, dadas las respuestas a los criterios de decisión, Azure IoT Hub es la mejor opción en este escenario.

# ¿Por qué no usar Azure IoT Central?
Azure IoT Central proporciona un panel que permite a las empresas administrar dispositivos de IoT de forma individual y en conjunto, ver informes y configurar notificaciones de error mediante una GUI. Pero, en este escenario, Tailwind Traders quiere integrar la telemetría que recopila y otra funcionalidad de análisis en una aplicación de software existente. Además, los electrodomésticos de la empresa solo van a recopilar datos mediante sensores y no necesitan la capacidad de actualizar la configuración o el software de forma remota. Por lo tanto, la empresa no necesita Azure IoT Central.

# ¿Por qué no usar Azure Sphere?
Azure Sphere proporciona una solución completa para escenarios en los que la seguridad es crítica. En este escenario la seguridad es preferible, pero no crítica. Los electrodomésticos no se pueden actualizar con nuevo software de forma remota. Los sensores simplemente notifican los datos de uso. Como resultado, Azure Sphere no es necesario.

# Uso de IoT Central
Tailwind Traders posee una flota de vehículos de entrega que transportan productos desde los almacenes hasta los centros de distribución y desde los centros de distribución hasta las tiendas y los hogares. La empresa está buscando una solución de logística completa que tome los datos enviados desde un equipo incorporado al vehículo y los convierta en información accionable.

Además, los envíos pueden equiparse con sensores de un proveedor de terceros para recopilar y supervisar las condiciones ambientales. Estos sensores pueden recopilar información como temperatura, humedad, inclinación, impacto, luz y ubicación de un envío.

Algunos de los objetivos de este sistema de logística incluyen:

- Supervisión del envío con seguimiento y trazabilidad en tiempo real
- Integridad del envío con supervisión de las condiciones ambientales en tiempo real
- Seguridad contra los robos, las pérdida o el daño de los envíos
- Geovallado, optimización de rutas, administración de flotas y análisis de vehículos
- Previsión para la salida y llegada predecibles de los envíos
- La empresa preferiría una solución precompilada para recopilar los datos del equipo del vehículo y del sensor, y proporcionar una interfaz gráfica de usuario que muestre informes sobre los envíos y los vehículos.

# ¿Qué servicio debe elegir?
Una vez más, aplique los criterios de decisión que ha conocido en las unidades anteriores.

En primer lugar, ¿es fundamental asegurarse de que el dispositivo o, en este caso, cada electrodoméstico, no esté en peligro? Idealmente, cada sensor y equipo de un vehículo sería inmune a las interferencias. Sin embargo, la seguridad no se mencionó como un problema crítico en este momento. Los sensores y los equipos de los vehículos son fabricados por un proveedor ajeno y, a menos que Tailwind Traders quiera fabricar sus propios dispositivos (que no es el caso), la empresa se verá obligada a usar hardware que ya está disponible.

En segundo lugar, ¿necesita Tailwind Traders un panel para la generación de informes y la administración? Sí, un panel de informes y administración es un requisito.

En función de estas respuestas a los criterios de decisión, Azure IoT Central es la mejor opción en este escenario. La plantilla de inicio Logística conectada proporciona un panel de serie que satisface muchos de estos requisitos. Este panel está preconfigurado para presentar la actividad crítica de operaciones de dispositivos de logística. Ciertamente es posible que se tenga que volver a configurar el panel para quitar las puertas de enlace de embarcaciones, pero la funcionalidad de puerta de enlace de camiones sería prácticamente exacta a lo que necesita Tailwind Traders.

# ¿Por qué no usar IoT Hub?
Si Tailwind Traders usa IoT Central, la empresa en realidad estaría usando un centro de IoT preconfigurado para sus necesidades específicas mediante la plantilla de inicio Logística conectada. De lo contrario, la empresa necesitaría realizar mucho desarrollo personalizado para compilar sus propios sistemas de administración y paneles basados en la nube sobre Azure IoT Hub.

# Uso de Azure Sphere
Tailwind Traders quiere implementar una solución de punto de venta táctil para la formalización de compras de autoservicio. Estos terminales de pago autoservicio deben ser ante todo seguros. Cada terminal debe ser impermeable al código malintencionado que podría crear transacciones fraudulentas, obligar a la empresa a desconectar los sistemas durante un período de compras intenso o enviar datos transaccionales a una organización de espías. Los terminales también deben comunicar información vital sobre el estado de la empresa y permitir actualizaciones seguras del software de forma remota.

Después de revisar muchas posibles soluciones durante el proceso de solicitud de ofertas, Tailwind Traders decide que necesita características que los proveedores aún no han implementado. En lugar de usar una solución existente, la empresa decide trabajar con una empresa de ingeniería líder especializada en soluciones de IoT. Este enfoque permite a la empresa compilar un terminal exclusivo y seguro que le proporciona una plataforma de venta directa sobre la que trabajar en adelante.

Aunque la empresa se centra principalmente en el propio terminal, Tailwind Traders se da cuenta de que quiere una solución que pueda ayudarle a comprender todos los datos que van a generar estos terminales en todas sus tiendas. Además, quiere una manera fácil de insertar actualizaciones de software en sus terminales.

# ¿Qué servicio debe elegir?
Una vez más, aplique los criterios de decisión como ha venido haciendo.

En primer lugar, ¿es fundamental asegurarse de que el dispositivo o, en este caso, cada terminal de punto de venta, no esté en peligro? Por supuesto. La seguridad del dispositivo es el requisito principal.

A continuación, ¿necesita Tailwind Traders un panel para la generación de informes y la administración? Sí, la empresa necesita un panel de informes y administración.

Por lo tanto, dadas las respuestas a los criterios de decisión, la empresa de ingeniería de IoT creará una plataforma basada tanto en Azure IoT Central como en Azure Sphere. Aunque no hay ninguna plantilla de inicio específica disponible en Azure IoT Central para este escenario, se puede adaptar una fácilmente para dar cabida a los tipos de informes que la empresa quiere ver y a las operaciones de administración que quiere realizar.

# ¿Por qué no elegir IoT Hub?
Con IoT Central, Tailwind Traders en realidad estaría usando también Azure IoT Hub en segundo plano.

# ¿Por qué no usar Azure Sphere?
Azure Sphere proporciona una solución completa para escenarios en los que la seguridad es crítica. En este escenario, la seguridad es ideal, pero no es una prioridad crítica. Aunque Azure Sphere proporciona una solución de un extremo a otro que incluye hardware, Tailwind Traders va a usar hardware de un proveedor ajeno. Por lo tanto, en este escenario, Azure Sphere no es necesario.

# Elija el mejor servicio de IA para sus necesidades!!!!!
# Introducción

La inteligencia artificial (IA) es una categoría de la informática que adapta y mejora su capacidad de toma de decisiones a lo largo del tiempo en función de sus éxitos y errores. Microsoft Azure proporciona varias soluciones de IA entre las que puede elegir, cada una de las cuales depende del problema que esté tratando de resolver.

Tailwind Traders, un distribuidor tradicional con tiendas físicas que ha experimentado un crecimiento explosivo de sus ventas en línea, se enfrenta a desafíos emocionantes en su cometido para mejorar sus operaciones de comercio electrónico y servicio. Los servicios de inteligencia artificial de Microsoft pueden ser una buena elección para una de las nuevas iniciativas de la empresa, pero Tailwind Traders necesita ayuda para comprender mejor qué opción de producto es mejor para cada escenario.

En este módulo, obtendrá información sobre los diferentes servicios de IA de Microsoft y analizará los criterios de decisión que los expertos usan para seleccionar el servicio adecuado para un escenario determinado.

# Objetivos de aprendizaje
Después de completar este módulo, podrá:

- Elegir los servicios de Azure AI que se adapten mejor a los desafíos empresariales a los que se enfrenta su organización
# Requisitos previos
- Familiaridad con el concepto de interfaces de programación de aplicaciones (API). Los programadores usan las API para interactuar con la funcionalidad que contienen las bibliotecas de código.

- Familiaridad con los siguientes conceptos adicionales:

_ API web: API a la que se puede acceder desde servidores que aceptan solicitudes a través de HTTP.
_ Punto de conexión de API web: ubicación de la biblioteca de código.
_ API de REST: diseño del estilo de dirección URL que se usa para exponer la funcionalidad de la API.

# Identificación de las opciones de producto
La IA es una clasificación amplia de la informática que permite que un sistema de software perciba su entorno y tome medidas que maximicen sus probabilidades de éxito a la hora de lograr sus objetivos. El objetivo de la IA es crear un sistema de software que pueda adaptarse o aprender algo por sí mismo sin estar programado explícitamente para hacerlo.

Existen dos enfoques básicos en la IA. El primero consiste en emplear un sistema de aprendizaje profundo que se modela en la red neuronal de la mente humana, lo que le permite descubrir, aprender y crecer a través de la experiencia.

El segundo enfoque es el aprendizaje automático, una técnica de la ciencia de datos que usa los datos existentes para entrenar un modelo, probarlo y aplicarlo a nuevos datos para pronosticar comportamientos, resultados y tendencias futuros.

Las previsiones o predicciones del aprendizaje automático pueden hacer que las aplicaciones y los dispositivos sean más inteligentes. Por ejemplo, al realizar una compra en línea, el aprendizaje automático impulsa los sistemas de recomendación de productos que ofrecen productos adicionales en función de lo que ha comprado y lo que han comprado otros compradores que han adquirido artículos similares en el pasado.

El aprendizaje automático también se usa para detectar fraudes de tarjetas de crédito analizando cada nueva transacción y usando lo que se ha aprendido a través del análisis de millones de transacciones fraudulentas.

# Opciones de producto de Azure
A grandes rasgos, Microsoft cuenta con tres ofertas de productos principales, cada una de las cuales está diseñada para una audiencia y un caso de uso concretos. Cada opción proporciona un conjunto diverso de herramientas, servicios y API de programación. En este módulo, simplemente vamos a ver aspectos superficiales de las funcionalidades de las opciones.

# Azure Machine Learning
Azure Machine Learning es una plataforma para realizar predicciones. Consta de herramientas y servicios que le permiten conectarse a los datos para entrenar y probar modelos para encontrar el que prediga con mayor precisión un resultado futuro. Una vez que ha ejecutado experimentos para probar el modelo, puede implementarlo y usarlo en tiempo real a través de un punto de conexión de API web.

Con Azure Machine Learning, puede realizar lo siguiente:

- Crear un proceso que defina cómo obtener los datos, cómo tratar los datos que faltan o que son incorrectos, cómo dividir los datos en un conjunto de entrenamiento o de pruebas y cómo enviar los datos al proceso de entrenamiento.
- Entrenar y evaluar modelos predictivos mediante herramientas y lenguajes de programación conocidos por los científicos de datos.
- Crear canalizaciones que definan dónde y cuándo ejecutar los experimentos de proceso intensivo necesarios para puntuar los algoritmos en función de los datos de entrenamiento y de prueba.
- Implementar el algoritmo de mejor rendimiento como una API en un punto de conexión para que otras aplicaciones puedan consumirlo en tiempo real.

Elija Azure Machine Learning cuando los científicos de datos necesiten un control completo sobre el diseño y el entrenamiento de un algoritmo con sus propios datos. En el vídeo siguiente se describen los pasos básicos necesarios para configurar un sistema de aprendizaje automático.

# Azure Cognitive Services
Azure Cognitive Services proporciona modelos de aprendizaje automático creados previamente que permiten a las aplicaciones ver, oír, hablar, comprender e incluso empezar a pensar. Use Azure Cognitive Services para solucionar problemas generales, como el análisis de texto para detectar opiniones o el análisis de imágenes para reconocer objetos o caras. No es necesario tener conocimientos de aprendizaje automático ni ciencia de datos para usar estos servicios. Los desarrolladores acceden a Azure Cognitive Services mediante API y pueden incluir fácilmente estas características en solo unas pocas líneas de código.

Si bien Azure Machine Learning requiere que traiga sus propios datos y entrene modelos a partir de esos datos, Azure Cognitive Services, en su mayor parte, proporciona modelos previamente entrenados para que pueda traer sus datos en directo a fin de obtener predicciones.

Azure Cognitive Services se puede dividir en las categorías siguientes:

- Servicios de lenguaje: permita que las aplicaciones procesen lenguaje natural con scripts precompilados, evalúen opiniones y aprendan a reconocer lo que quieren los usuarios.
- Servicios de voz: convierta voz en texto y texto en voz de sonido natural. Traduzca de un idioma a otro y habilite el reconocimiento y la verificación del hablante.
- Servicios de visión: agregue capacidades de reconocimiento e identificación al analizar imágenes, vídeos y otro contenido visual.
- Servicios de decisión: agregue recomendaciones personalizadas para cada usuario que mejoren automáticamente cada vez que se usen, modere contenido para supervisar y quitar el - contenido ofensivo o arriesgado y detecte anomalías en los datos de series temporales.

# Azure Bot Service
Azure Bot Service y Bot Framework son plataformas para crear agentes virtuales que comprenden y responden a preguntas como un ser humano. Azure Bot Service se diferencia de Azure Machine Learning y Azure Cognitive Services en que tiene un caso de uso concreto: crear un agente virtual que pueda comunicarse de forma inteligente con los usuarios. En segundo plano, el bot que crea usa otros servicios de Azure, como Azure Cognitive Services, para comprender lo que solicitan sus homólogos humanos.

Los bots se pueden usar para convertir tareas sencillas y repetitivas, como tomar una reserva de cena o recopilar información de perfil, en sistemas automatizados que ya no requieran la intervención humana directa. Los usuarios conversan con un bot mediante texto, tarjetas interactivas y voz. Una interacción con un bot puede ser tanto una pregunta y una respuesta rápidas como una conversación sofisticada que proporciona acceso a servicios de forma inteligente.

# Análisis de los criterios de decisión
En esta unidad, analizará los criterios que emplean los expertos para elegir un servicio de IA para una determinada necesidad empresarial. Comprender estos criterios también puede ayudar a entender mejor las diferencias entre los productos.

# ¿Está creando un agente virtual que interactúa con seres humanos mediante el lenguaje natural?
Use Azure Bot Service cuando necesite crear un agente virtual para interactuar con los usuarios mediante el lenguaje natural. Bot Service integra orígenes de conocimiento, procesamiento de lenguaje natural y factores de forma para permitir la interacción entre distintos canales.

Las soluciones de Bot Service normalmente se basan en otros servicios de IA para cuestiones como la comprensión del lenguaje natural o incluso la traducción para localizar las respuestas al idioma preferido del cliente.

Antes de entrar de pleno en la creación de una experiencia de chat personalizada con Bot Service, puede que sea mejor buscar soluciones precompiladas sin código que abarquen los escenarios habituales. Por ejemplo, puede emplear QnA Maker, disponible en Azure Marketplace, para crear, entrenar y publicar un bot sofisticado que use páginas de preguntas más frecuentes, sitios web de soporte técnico, manuales de productos, documentos de SharePoint o contenido editorial a través de una interfaz de usuario fácil de usar o mediante las API de REST.

# ¿Necesita un servicio que pueda comprender el contenido y el significado de imágenes, vídeos y audios o traducir texto a un idioma diferente?
Use Azure Cognitive Services cuando necesite realizar tareas de uso general, como la conversión de voz en texto, la integración con búsquedas o la identificación de objetos en una imagen. Azure Cognitive Services es de uso general, lo que significa que muchos tipos diferentes de clientes pueden beneficiarse del trabajo que Microsoft ya ha llevado a cabo para entrenar y probar estos modelos y ofrecerlos de forma económica a escala.
# ¿Necesita predecir el comportamiento del usuario o proporcionar a los usuarios recomendaciones personalizadas en la aplicación?
El servicio Azure Cognitive Services Personalizer supervisa las acciones de los usuarios en una aplicación. Puede usar Personalizer para predecir su comportamiento y proporcionar experiencias relevantes a medida que identifique patrones de uso. De nuevo, podría capturar y almacenar el comportamiento del usuario y crear su propia solución de Azure Machine Learning personalizada para realizar estas acciones, pero este enfoque requeriría mucho esfuerzo y gastos.
# ¿La aplicación predecirá resultados futuros a partir de datos históricos privados?
Elija Azure Machine Learning cuando necesite analizar datos para predecir resultados futuros. Por ejemplo, supongamos que necesita analizar transacciones financieras realizadas durante años para detectar nuevos patrones que podrían ayudarle a crear nuevos productos y servicios para los clientes de su empresa y ofrecer esos nuevos servicios durante las llamadas rutinarias del servicio al cliente. Al trabajar con datos de propiedad, es probable que necesite crear un modelo de aprendizaje automático más personalizado y adaptado.
# ¿Necesita crear un modelo con sus propios datos o realizar una tarea distinta de las mencionadas anteriormente?
Use Azure Machine Learning para obtener la máxima flexibilidad. Los científicos de datos y los ingenieros de IA pueden usar las herramientas con las que están familiarizados y los datos que les proporcione para desarrollar modelos de aprendizaje profundo y de aprendizaje automático adaptados a sus requisitos particulares.

# Uso de Machine Learning para sistemas de ayuda a la toma de decisiones

El sitio web de comercio electrónico de Tailwind Traders permite a los clientes examinar y comprar artículos que se pueden entregar o recoger en la tienda de venta directa más cercana a su ubicación.

El equipo de marketing está convencido de que puede aumentar drásticamente las ventas si sugiere productos adicionales que complementen los artículos del carro del comprador en el momento de finalizar la compra. El equipo podría codificar estas sugerencias de forma rígida, pero considera que un enfoque más orgánico sería usar los datos de ventas de varios años, así como las nuevas tendencias de compra, para decidir qué productos se muestran al comprador. Además, las sugerencias pueden verse influidas por la disponibilidad del producto o su rentabilidad, entre otros factores.

Los expertos en ciencia de datos del equipo de marketing ya han realizado algún análisis inicial del dominio del problema y han determinado que pueden tardar meses en crear un prototipo y, posiblemente, un año en implementarlo.

# ¿Qué servicio debe elegir?

Vamos a aplicar los criterios de decisión que hemos aprendido en la unidad anterior para encontrar la opción adecuada.

En primer lugar, ¿Tailwind Traders está creando un agente virtual que interactúa con seres humanos mediante el lenguaje natural? No, por lo que Azure Bot Service no es un buen candidato para este escenario.

En segundo lugar, ¿Tailwind Traders necesita un servicio que pueda comprender el contenido y el significado de imágenes, vídeos y audios o traducir texto a un idioma diferente? No, por lo que Cognitive Services no ayudará a la empresa.

En tercer lugar, ¿Tailwind Traders necesita predecir el comportamiento del usuario o proporcionar recomendaciones personalizadas a los usuarios? Sí. Sin embargo, la creación de recomendaciones basadas en el comportamiento del usuario es solo una parte del requisito. Tailwind Traders necesita crear un modelo complejo que incorpore datos históricos de ventas, datos de tendencias de ventas, inventario, etc. Es posible que el servicio Azure Cognitive Services Personalizer pueda desempeñar una función, pero no podría abordar toda la amplitud del proyecto por sí solo.

En cuarto lugar, ¿la aplicación de Tailwind Traders predecirá resultados futuros a partir de datos históricos privados? Sí, y por este motivo, en este escenario, Azure Machine Learning es probablemente la mejor opción.

El éxito de este esfuerzo dependerá principalmente de la capacidad del modelo para seleccionar con precisión los productos de venta adecuados que se sugieren al comprador. Dado que el modelo tendría que ajustarse y retocarse con el tiempo, es probable que un producto listo para usarse no sea suficiente.

Por último, parece que el equipo de marketing ya cuenta con algunos expertos en ciencia de datos, y el equipo está dispuesto a realizar al menos un compromiso de un año para compilar, probar y retocar los modelos que se van a usar.

# Uso de Cognitive Services para el análisis de datos 
La primera generación del sitio web de comercio electrónico de Tailwind Traders solo se encontraba disponible en inglés. Pero cuando el equipo de marketing patrocinó un estudio demográfico para las tiendas físicas de la empresa, descubrió que, de media, solo el 80 % de los clientes potenciales hablan inglés. En algunos barrios, ese número se reduce al 50 %. El equipo considera que agregar varios idiomas es una oportunidad magnífica para proporcionar a los clientes que no hablan en inglés la misma experiencia de comercio electrónico que se ofrece a los clientes anglófonos.
# ¿Qué servicio debe elegir?
Al igual que en la unidad anterior, debe aplicar los criterios de decisión que ha aprendido para encontrar la opción adecuada.

En primer lugar, ¿Tailwind Traders está creando un agente virtual que interactúa con seres humanos mediante el lenguaje natural? No, por lo que Azure Bot Service no es un buen candidato para este escenario. Aun así, en el caso de que Tailwind Traders implemente un agente de servicio al cliente, es posible que quiera considerar el uso de la API Translator para proporcionar traducción en tiempo real con el fin de ayudar a los clientes que no son anglófonos.

En segundo lugar, ¿Tailwind Traders necesita un servicio que pueda comprender el contenido y el significado de imágenes, vídeos y audios o traducir texto a un idioma diferente? Sí. La traducción de contenido textual de un idioma a otro es una tarea de uso general que se puede simplificar mediante el servicio Translator de Azure Cognitive Services. El servicio es fácil de integrar en sus aplicaciones, sitios web, herramientas y soluciones. Permite agregar experiencias de usuario multilingües en más de 60 idiomas y se puede usar en cualquier plataforma de hardware con cualquier sistema operativo para la traducción de texto a texto.

Azure Cognitive Services es probablemente la mejor opción para este escenario, pero vamos a seguir aplicando los criterios de decisión para asegurarnos.

En tercer lugar, ¿Tailwind Traders necesita predecir el comportamiento del usuario o proporcionar recomendaciones personalizadas a los usuarios? No, por lo que el servicio Personalizer de Azure Cognitive Services no es un buen candidato para este escenario.

Por último, ¿la aplicación de Tailwind Traders necesitará predecir resultados futuros a partir de datos históricos privados? No. Aunque sería posible crear un modelo de aprendizaje automático para realizar la traducción a varios idiomas, sería costoso y lento para Tailwind Traders intentar compilar sus propios modelos de traducción. El equipo no tienen la competencia en aprendizaje profundo ni los datos lingüísticos necesarios para entrenar los modelos.

Ahora que ha examinado todos los criterios de los expertos, puede seleccionar con confianza Cognitive Services como la mejor opción de producto para este escenario.

# Uso de Bot Service para experiencias interactivas de chat

El equipo de servicio al cliente ha solicitado durante mucho tiempo un agente virtual para que se ocupe de la inmensa mayoría de las preguntas que se le pidan. A pesar de destacar las respuestas a las preguntas más frecuentes en el sitio web, los compradores son impacientes y creen que contactar mediante una ventana de chat les ahorra tiempo.

El equipo quiere que los compradores se sientan como si estuvieran interactuando con un ser humano real. Cuando quede claro que el agente virtual no puede proporcionar una respuesta, la sesión de chat se debería transferir a un agente humano.

El hecho de ofrecer un agente virtual reduciría la cantidad de tiempo que tardan los compradores en recibir respuestas. El agente virtual podría responder a la mayoría de las preguntas, lo que permitiría a los agentes del servicio de atención al cliente proporcionar soporte técnico a preguntas más difíciles o problemas relacionados con las cuentas.

# ¿Qué servicio debe elegir?
Una vez más, aplique los criterios de decisión con los que ya está familiarizado para encontrar el producto adecuado.

En primer lugar, ¿Tailwind Traders está creando un agente virtual que interactúa con seres humanos mediante el lenguaje natural? Sí. Azure Bot Service debería usarse en este escenario para implementar una experiencia de chat de agente virtual. Bot Service podría beneficiarse de información incluida en la página de preguntas más frecuentes del sitio web, junto con miles de sesiones de chat almacenadas entre compradores y representantes del servicio al cliente. Los supervisores del servicio de atención al cliente pueden probar y retocar las respuestas para seguir refinando la experiencia de chat.

Aunque es probable que ya haya encontrado la mejor opción para este escenario, siga aplicando los criterios de decisión para ver si hay opciones adicionales que también funcionen.

En segundo lugar, ¿Tailwind Traders necesita un servicio que pueda comprender el contenido y el significado de imágenes, vídeos y audios o traducir texto a un idioma diferente? Posiblemente, sí. En este escenario, Azure Cognitive Services podría usarse junto con Bot Service para compilar la solución. Para acelerar la implementación, los desarrolladores podrían explorar el uso de soluciones precompiladas, como QnA Maker (parte de Cognitive Services) o Power Virtual Agents. Además, cualquier solución de bot de Azure podría implementar varios servicios de Azure Cognitive Services, como Language Understanding (LUIS) y, posiblemente, Translator para traducir del idioma del comprador al inglés y viceversa.

En tercer lugar, ¿Tailwind Traders necesita predecir el comportamiento del usuario o proporcionar recomendaciones personalizadas a los usuarios? No. Azure Cognitive Services Personalizer no es un buen candidato para este escenario.

Por último, ¿la aplicación de Tailwind Traders necesitará predecir resultados futuros a partir de datos históricos privados? No. Aunque Tailwind Traders tiene datos históricos para alimentar un modelo, lo que permitiría usar Azure Machine Learning para crear una solución de chat, ya existe otra opción que está adaptada a la experiencia del bot de chat.
