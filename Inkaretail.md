UNIVERSIDAD NACIONAL DE SAN CRISTÓBAL DE HUAMANGA
FACULTAD DE INGENIERÍA DE MINAS, GEOLOGÍA Y CIVIL
ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS
<img width="338" height="453" alt="image" src="https://github.com/user-attachments/assets/661444c5-8d7d-4d61-956d-85fd64b48749" />

Asignatura	: Pruebas y Aseguramiento de la Calidad de Software
Docente 	: Ing. LIZBETH JAICO QUISPE
Estudiantes:
-	QUISPE CCAHUANA, María Leonela
-	VILA CAYO,, Nayherly Dianeth

URL Informe: https://docs.google.com/document/d/1XZFDVMgJgAmH-in3mwyvXbCPCqzyRPY1uKCyPcITnXs/edit?usp=sharing 

Descripción general del Sistema:
InkaRetail S.A.C. es una empresa de retail con 12 tiendas en Ayacucho, Huancayo y Cusco que está desarrollando el SGI (Sistema de Gestión de Inventario), una aplicación web que permite a los usuarios autenticarse, acceder al inventario de productos y gestionar el stock de cada tienda. El sistema ofrece funcionalidades como inicio de sesión seguro con roles (Administrador, Vendedor, Jefe de Almacén), registro de nuevos usuarios con validación de contraseña, consulta y actualización de stock, generación de alertas por stock bajo y emisión de reportes. Cuenta con validaciones de negocio en todos los formularios, proporcionando una experiencia segura y accesible desde cualquier navegador.

Descripción de funcionalidades:
Funcionalidad de Login: La funcionalidad de Login permite a los usuarios acceder de forma segura a sus cuentas ingresando su correo electrónico y contraseña registrados. El sistema valida las credenciales proporcionadas y, si son correctas, concede el acceso al panel principal personalizado, donde el usuario puede continuar con sus cursos, ver su progreso y acceder a todos los recursos disponibles. En caso de que las credenciales sean incorrectas, el sistema muestra un mensaje de error indicando que los datos no son válidos, sin permitir el acceso.
Funcionalidad de Registro: La funcionalidad de Registro permite a los usuarios crear una cuenta de forma segura ingresando un correo electrónico y contraseña. El sistema valida los datos proporcionados y, si son correctos, concede el registro en la base de datos. En caso de que las credenciales sean incorrectas, el sistema muestra un mensaje de error indicando que los datos no son válidos, sin permitir el registro.

RTM: https://docs.google.com/spreadsheets/d/1s9VbpJEn4LHq_J4razM95Jmul9vTOWBnaYyfcD3uAiI/edit?usp=sharing 
<img width="1121" height="604" alt="image" src="https://github.com/user-attachments/assets/56d04229-cea9-475c-92ba-79ff1012ea29" />

GAPs encontrados con sus TCs nuevos diseñados:
Se detectaron dos GAPs correspondiente al criterio de aceptación CA-4 y CA-5 que carecen de casos de prueba (TC). 
Detalles de los criterios de aceptación:
CA-4: Si la contraseña no cumple las reglas de seguridad → el sistema indica qué regla se está violando.
CA-5: Si algún campo está vacío → el sistema pide completar los campos antes de continuar.

TC-010: Registro con todos los campos vacíos
IDENTIFICADOR: TC-009
DESCRIPCIÓN: Iniciar sesión en el SGI InkaRetail: Verificar que un usuario nuevo no puede crear una cuenta con una contraseña débil.
PRECONDICIONES: El email nuevo.usuario@inkaretail.com NO debe existir en el sistema.
DATOS DE ENTRADA: Nombre: Pedro Condori | Email: pedro.condori@inkaretail.com | Password: Pedro | Confirmar: Pedro2024! | Rol: Vendedor
PASOS A SEGUIR
1. Ir a la página de registro en el navegador.
2. Verificar que la pestaña 'Registrar' esta activa.
3. Ingresar en el campo Nombre: Pedro Condori
4. Ingresar en el campo Email: pedro.condori@inkaretail.com
5. Ingresar en el campo Password: Pedro
6. Ingresar en el campo Confirmar Password: Pedro
7. Ingresar en el campo Rol: Vendedor
5. Hacer clic en el botón 'Registrar'.
6. Observar el mensaje que aparece.
RESULTADO ESPERADO: El sistema muestra el mensaje 'Mínimo 8 caracteres'.
ESTADO: Progress
TÉCNICA: PE: Clase Válida
PRIORIDAD: ALTA

TC-009: Registro con contraseña débil
IDENTIFICADOR: TC-010
DESCRIPCIÓN: Iniciar sesión en el SGI InkaRetail: Verificar que un usuario nuevo puede crear una cuenta con todos los datos correctos.
PRECONDICIONES: El email nuevo.usuario@inkaretail.com NO debe existir en el sistema.
DATOS DE ENTRADA: No completar ningún campo.
PASOS A SEGUIR: 
1. Ir a la página de registro en el navegador.
2. Verificar que la pestaña 'Registrar' esta activa.
3. Dejar los campos vacíos.
4. Hacer clic en el botón 'Registrar'.
5. Observar el mensaje que aparece.
RESULTADO ESPERADO: El sistema muestra el mensaje 'Completar todos los campos'. NO se abre un popup de bienvenida.
ESTADO: To Do
TÉCNICA: PE: Clase Válida
PRIORIDAD: MEDIA

EVIDENCIAS JIRA:
Vista de la Story HU-031 con todos sus Sub-tasks (TC-001 a TC-005) visibles.
<img width="828" height="521" alt="image" src="https://github.com/user-attachments/assets/5f03d830-af5e-40b5-856c-f08aef8b974a" />

Vista de la Story HU-032 con todos sus Sub-tasks (TC-006 a TC-010) incluyendo los GAPs.
<img width="824" height="523" alt="image" src="https://github.com/user-attachments/assets/f8d32b64-eb12-4989-b74e-ac76ecc76453" />

Vista de un TC con el link 'is blocked by [Bug]' si hubo algún FAIL.
<img width="826" height="527" alt="image" src="https://github.com/user-attachments/assets/d3dd2e69-7a97-4f10-beab-8b017c119367" />

Board del proyecto mostrando la distribución de tareas por estado.
<img width="816" height="560" alt="image" src="https://github.com/user-attachments/assets/2bfcf90a-ba50-428e-b36d-29db48dd6768" />


CONCLUSIONES:
- La implementación de la Matriz de Trazabilidad de Requisitos (RTM) demostró ser una herramienta indispensable en el aseguramiento de la calidad (QA). Al vincular de forma bidireccional las Historias de Usuario (HU), sus Criterios de Aceptación (CA) y los Casos de Prueba (TC), se garantiza que toda HU quede validada. 
- El diseño e incorporación de nuevos escenarios de prueba para cubrir los GAPs demuestra que la trazabilidad no es un proceso puramente documental, sino un mecanismo de control preventivo que elimina los "puntos ciegos" antes del cierre del Sprint.
- La réplica de la estructura de QA dentro de Jira y el uso del tablero Kanban facilitaron la centralización del flujo de trabajo. Asimismo, la utilización de enlaces semánticos como "is blocked by" entre un Caso de Prueba fallido (FAIL) y un Bug permite automatizar la visibilidad del estado real del proyecto.
