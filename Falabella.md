UNIVERSIDAD NACIONAL DE SAN CRISTÓBAL DE HUAMANGA

FACULTAD DE INGENIERÍA DE MINAS, GEOLOGÍA Y CIVIL

ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS

<img width="338" height="453" alt="image" center src="https://github.com/user-attachments/assets/661444c5-8d7d-4d61-956d-85fd64b48749" />

Asignatura : Pruebas y Aseguramiento de la Calidad de Software

Docente : Ing. LIZBETH JAICO QUISPE

Estudiantes:

- QUISPE CCAHUANA, María Leonela
- VILA CAYO, Nayherly Dianeth

URL Informe: https://docs.google.com/document/d/1ACH-7gG-8VqqPSSI9rQfr0rhwAaqrIBNVuRV3aowQFE/edit?usp=sharing 

1. Descripción general del Sistema

Falabella S.A.C. (Saga Falabella Perú) se consolida como una de las principales cadenas de retail del país, operando bajo una plataforma transaccional de tipo Business-to-Consumer (B2C) de alta concurrencia y escala nacional. Su modelo de negocio unifica múltiples unidades estratégicas —como tiendas por departamentos, supermercados, mejoramiento del hogar y un marketplace de terceros— bajo un único ecosistema omnicanal eficiente.
A través de su plataforma de comercio electrónico (www.falabella.com.pe), millones de clientes peruanos tienen la posibilidad de explorar y adquirir productos de moda, tecnología, hogar, deportes y más. El sistema cuenta con una arquitectura web optimizada para la navegación responsiva, garantizando una experiencia accesible, fluida y adaptada a cualquier dispositivo móvil o de escritorio con conexión a internet.

Funcionalidades Clave del Sistema

La plataforma está diseñada para ofrecer una experiencia de usuario intuitiva y de alto rendimiento a través de las siguientes capacidades:
- Catálogo Masivo e Interactivo: Consulta dinámica de productos estructurados rigurosamente por categorías para facilitar la búsqueda.
- Gestión Comercial Dinámica: Administración y persistencia de elementos dentro del Carrito de Compras en tiempo real.
- Control de Usuarios: Autenticación segura y registro de nuevas cuentas con validación automatizada de datos personales.
- Administración Logística: Gestión avanzada de direcciones de despacho y un sistema integrado para el seguimiento de pedidos.


2. Descripción de funcionalidades

Login: La funcionalidad de Login permite a los clientes de Falabella Perú acceder de forma segura a su cuenta personal ingresando su correo electrónico y contraseña registrados en la plataforma. El sistema valida las credenciales proporcionadas y, si son correctas, concede el acceso al panel principal del usuario, donde puede visualizar sus pedidos, lista de deseos, datos personales y continuar con sus compras. En caso de que las credenciales sean incorrectas o el correo no esté registrado, el sistema muestra un mensaje de error específico sin permitir el acceso, protegiendo así la seguridad de la cuenta.
Registro: La funcionalidad de Registro permite a nuevos usuarios crear una cuenta personal en Falabella Perú completando un formulario con sus datos personales: nombre, apellidos, correo electrónico, contraseña, número de documento de identidad (DNI), fecha de nacimiento y número de celular. El sistema valida cada campo en tiempo real, verificando que el correo no esté previamente registrado, que la contraseña cumpla los requisitos mínimos de seguridad y que ambas contraseñas ingresadas coincidan. Al completar el registro exitosamente, el sistema crea la cuenta, muestra un mensaje de bienvenida e inicia sesión automáticamente redirigiendo al usuario al home de la tienda.
Búsqueda y Filtro de Productos: La funcionalidad de Búsqueda y Filtros de Productos permite a los usuarios indexar de forma inmediata el catálogo de Falabella, además permite localizar artículos específicos dentro de una base de datos de millones de registros. Incorpora:
- Barra de búsqueda predictiva: Sugiere términos populares, marcas o productos a medida que el usuario digita.
- Procesamiento de consultas de texto: Filtra resultados basados en concordancias semánticas, categorías, códigos de producto (SKU) y marcas.
- Sanitización de entradas: Procesa y neutraliza caracteres no permitidos o código malicioso.
- Manejo de estados vacíos: Despliega flujos alternos e informativos cuando no se encuentran coincidencias directas en la base de datos de productos.
- Módulo de filtros avanzados: Permite refinar la galería de productos por rango numérico de precios (mínimo y máximo), marcas, colores y tallas.
Carrito de Compras: La funcionalidad de Carrito de Compras permite consolidar y persistir temporalmente la selección de productos del usuario antes de proceder al pago. Administra reglas de negocio cruciales como:
- Verificación de stock e inventario: Valida la disponibilidad de productos en tiempo real.
- Control de variantes: Obliga a seleccionar parámetros clave como color o talla antes de permitir la adición del producto.
- Ajuste dinámico de cantidades: Gestiona el incremento o decremento de ítems respetando los límites mínimos (N=1) y los límites máximos disponibles en almacén.
Checkout: La funcionalidad de Checkout permite capturar los datos de contacto de los usuarios por medio de un registro de correos electrónicos para el envío de comprobantes electrónicos, además de validar y aplicar cupones de descuento vigentes sobre el subtotal de una compra. Por último captura y valida la información del medio de pago (tarjeta de crédito/débito u otro medio de pago), impidiendo el envío de datos en blanco o con formatos incorrectos. 


3. Contexto del Sprint

Como parte del proceso de aseguramiento de la calidad del portal web de Falabella Perú, se ha definido el ciclo de vida del proyecto de pruebas mediante la segmentación de los requerimientos técnicos y funcionales en tres (03) Sprints estratégicos. Esta planificación permite ejecutar las validaciones de manera incremental y controlada, priorizando los módulos críticos del e-commerce de acuerdo con las dependencias funcionales y necesidades del negocio.
Asimismo, se ha desarrollado la Matriz de Trazabilidad de Requisitos (RTM) con el objetivo de garantizar la cobertura integral de los requerimientos y criterios de aceptación definidos para cada funcionalidad. En alineación con las directrices establecidas por el Product Owner y la Scrum Master, ningún módulo podrá ser liberado a producción si presenta criterios de aceptación sin sus respectivos casos de prueba asociados en la RTM.
Esta medida asegura la trazabilidad completa entre requerimientos, criterios de aceptación y evidencias de validación, reduciendo riesgos funcionales y garantizando la calidad del producto antes de su despliegue en ambientes productivos.


4. Historias de usuario

<img width="471" height="368" alt="image" src="https://github.com/user-attachments/assets/e2b43ad8-590a-407c-9104-74f3d423f700" />

5. Criterios de aceptación

HU-001: Autenticación (Login)

- CA-1.1: Si el usuario registrado ingresa su correo electrónico y contraseña correctos en el formulario -> el sistema muestra un popup de bienvenida con su nombre, inicia la sesión web y redirige al home con el nombre del cliente visible en la cabecera. 
- CA-1.2: Si el usuario ingresa su correo registrado pero con una contraseña incorrecta -> el sistema muestra un mensaje de error notificando la credencial inválida, bloquea el inicio de sesión y mantiene al usuario en la interfaz de login.


HU-002: Registro de Usuarios

- CA-2.1: Si un usuario intenta crear una cuenta utilizando un correo electrónico que ya existe en la base de datos -> el sistema impide la creación de la cuenta duplicada, muestra la advertencia "Este correo ya está registrado" y mantiene los datos del formulario intactos para su edición.
- CA-2.2: Si un usuario introduce un correo electrónico con formato de sintaxis inválido (sin @ o dominio) -> el sistema bloquea el envío del formulario de registro, resalta el campo de email en rojo y despliega la advertencia "Ingresa un correo electrónico válido".
- CA-2.3: Si un nuevo usuario ingresa una contraseña que cumple exactamente con el límite mínimo de 8 caracteres (N) y rellena los demás campos con valores válidos -> el sistema valida la contraseña como segura, crea la cuenta de forma exitosa y redirige al home con la sesión iniciada.
- CA-2.4: Si un usuario ingresa un número de celular con formato inválido (con letras o con longitud distinta a 9 dígitos) -> el sistema bloquea el envío del registro, resalta el campo de teléfono e indica el error de formato mediante la advertencia "Ingresa un número de celular válido".
  

HU-003: Búsqueda y Filtros

- CA-3.1: Si el usuario ingresa una palabra clave existente en la barra de búsqueda -> el sistema despliega la galería de productos coincidentes con filtros laterales activos y muestra el número total de resultados.
- CA-3.2:Si el usuario ingresa caracteres especiales, símbolos o código script (<script>alert('xss')</script>, %$#@!) en la barra de búsqueda → el sistema sanitiza la entrada, neutraliza cualquier intento de ejecución de código malicioso, no expone trazas de error del servidor y despliega un estado de búsqueda vacío sin redirigir.
- CA-3.3: Si el usuario modifica manualmente la URL del filtro de precios con valores de texto no válidos -> el sistema en el backend ignora el parámetro corrupto, recarga la búsqueda por defecto de forma segura y evita colapsar el servidor.
- CA-3.4: Si el usuario ingresa un término de texto válido y bien formado que no corresponde a ningún producto del catálogo (ej: "xqz99productofalso") → el sistema muestra la página de "Sin resultados", sugiere categorías o búsquedas alternativas relacionadas y no lista ningún producto en la galería.
- CA-3.5: Si el usuario presiona Enter o hace clic en la lupa con el campo de búsqueda completamente vacío -> el sistema no procesa ninguna consulta, permanece en la página actual y no redirecciona a interfaces de resultados vacías. 


HU-004: Carrito de compras

- CA-4.1: Si el usuario agrega un artículo estándar con stock disponible a la bolsa -> el sistema añade el producto al carrito, muestra un popup de confirmación e incrementa el contador visual.
- CA-4.2: Si el usuario intenta agregar un calzado o prenda de vestir sin haber seleccionado la talla -> el sistema impide la adición a la bolsa y resalta visualmente en rojo el selector de variantes obligatorias.
- CA-4.3: Si el usuario reduce la cantidad de un artículo en el carrito por debajo de 1 -> el sistema bloquea el botón de decremento (-) en 1 o solicita una confirmación física para eliminar el ítem.
- CA-4.4: Si el usuario intenta seleccionar una cantidad superior al stock físico en almacén (N+1) -> el sistema impide la selección, restringe el control numérico y muestra una alerta indicando la falta de disponibilidad de inventario.
- CA-4.5: Si el usuario hace clic en el ícono de eliminar de cada producto y confirma la acción de remoción hasta vaciar la bolsa -> el sistema muestra el mensaje de alerta "Tu carrito está vacío", actualización del contador de la bolsa a 0 y habilita el botón para continuar comprando. 


HU-005: Checkout

- CA-5.1: Si el usuario ingresa datos válidos de una tarjeta de crédito activa y autorizada -> el sistema procesa la transacción exitosamente con el banco, vacía la bolsa y redirige a la pantalla de éxito con el número de orden de compra.
- CA-5.2: Si el usuario registra un correo electrónico de facturación con formato de sintaxis inválido (sin @ o dominio) -> el sistema detiene el avance en el checkout y notifica con una alerta visual de error de formato.
- CA-5.3: Si el usuario ingresa un código de cupón de descuento inexistente en la base de datos -> el sistema rechaza el cupón mostrando una alerta de error y mantiene intactos los montos económicos de la bolsa de compra.
- CA-5.4: Si el usuario envía el formulario de pago rellenando los campos requeridos de la tarjeta únicamente con espacios en blanco -> el sistema ejecuta un recorte de espacios (trim), detiene el envío de datos financieros y marca los campos como obligatorios.


6. RTM

URL: https://docs.google.com/spreadsheets/d/1qfietvuF-M3nCqvuq-hIAowghqYMQDnDFJRePJPpX-A/edit?usp=sharing 

<img width="1151" height="523" alt="image" src="https://github.com/user-attachments/assets/67d9d490-95ae-43b9-b225-b532286ecb39" />


7. GAPs

Se detectó un GAP correspondiente al criterio de aceptación CA-3.4 que carece de un caso de prueba (TC). 
Detalle del criterio de aceptación CA-3.4: Si el usuario ingresa un término de texto válido y bien formado que no corresponde a ningún producto del catálogo → el sistema muestra la página de "Sin resultados", sugiere categorías o búsquedas alternativas relacionadas y no lista ningún producto en la galería. 

<img width="922" height="931" alt="image" src="https://github.com/user-attachments/assets/a37c258c-3ee5-423d-8e14-a01dd83f13e4" />


8. Evidencias

Vista de la Story HU-001 con todos sus Sub-tasks (TC-001 a TC-002) visibles.

<img width="536" height="343" alt="image" src="https://github.com/user-attachments/assets/9e3623b1-7d72-440b-b1ec-d7ed40a64fe2" />

Vista de la Story HU-002 con todos sus Sub-tasks (TC-003 a TC-006) visibles.

<img width="539" height="313" alt="image" src="https://github.com/user-attachments/assets/b7ae6a3f-3d70-4ddf-8077-4302a71a6c26" />

Vista de la Story HU-003 con todos sus Sub-tasks (TC-007 a TC-010, TC-020) incluyendo los GAPs.

<img width="523" height="339" alt="image" src="https://github.com/user-attachments/assets/84e39291-2b43-4153-af9a-f0b8ea49adcb" />

Vista de la Story HU-004 con todos sus Sub-tasks (TC-011 a TC-015) visibles.

<img width="536" height="345" alt="image" src="https://github.com/user-attachments/assets/5a1a6661-3c54-42f9-9113-ade8961343ca" />

Vista de la Story HU-005 con todos sus Sub-tasks (TC-016 a TC-019) visibles.

<img width="539" height="346" alt="image" src="https://github.com/user-attachments/assets/9cfd14af-ac1b-46b7-88bf-fc7a54103753" />

Board del proyecto mostrando la distribución de tareas por estado.

<img width="909" height="661" alt="image" src="https://github.com/user-attachments/assets/88a5c548-ec4e-43fe-8a8c-8d4ff3537446" />


9. Conclusiones
   
- La implementación de la Matriz de Trazabilidad de Requisitos (RTM) demostró ser una herramienta indispensable en el aseguramiento de la calidad (QA). Al vincular de forma bidireccional las Historias de Usuario (HU), sus Criterios de Aceptación (CA) y los Casos de Prueba (TC), se garantiza la validación completa del sistema. Para una plataforma de alta concurrencia como el e-commerce de Falabella, esto reduce drásticamente el riesgo de desplegar a producción funcionalidades críticas (como la autenticación o pasarelas de pago).
- El análisis de GAPs permitió identificar criterios de aceptación que carecían de una prueba asignada en la planificación inicial. El diseño e incorporación de nuevos escenarios de prueba para cubrir estos vacíos demuestra que la trazabilidad no es un proceso puramente documental, sino un mecanismo de control preventivo que elimina los "puntos ciegos" antes del cierre del Sprint.
- La réplica de la estructura de QA dentro de Jira (Epics, Stories y Sub-tasks) y el uso del tablero Kanban facilitaron la centralización del flujo de trabajo. Esto agiliza la comunicación interfuncional entre los equipos de Desarrollo y Testing, acelerando los tiempos de corrección de software.
- El almacenamiento, respaldo y versionamiento tanto de la matriz en Excel como del informe técnico dentro de un repositorio de Git asegura la integridad y la auditoría transparente del proceso de pruebas. Esta práctica alinea el entorno educativo con las metodologías modernas de desarrollo y entrega continua (CI/CD), donde la documentación de la calidad debe ser tan trazable e histórica como el código fuente mismo.

