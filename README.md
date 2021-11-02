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
