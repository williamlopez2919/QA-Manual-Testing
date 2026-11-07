# Módulo de Autenticación (Login) - Escenarios y Casos de Prueba

## 👤 User Story

**Como** usuario registrado,  
**quiero** iniciar sesión con mi correo y contraseña  
**para** acceder a mi cuenta y realizar operaciones de forma segura.

---

## 📌 Tabla General de Escenarios de Prueba (Test Scenarios)

| Scenario ID | Test Scenario | Description |
| --- | --- | --- |
| **TS-001** | Login con credenciales válidas | Verificar que un usuario pueda iniciar sesión utilizando un correo y contraseña correctos. |
| **TS-002** | Login con contraseña incorrecta | Verificar que el sistema rechace una contraseña incorrecta y proteja la cuenta. |
| **TS-003** | Login con correo incorrecto | Verificar que el sistema rechace un correo electrónico que no está registrado. |
| **TS-004** | Login con campos vacíos | Verificar que el sistema valide y bloquee los campos obligatorios si se envían en blanco. |
| **TS-005** | Login con formato de correo inválido | Verificar que el sistema valide el formato correcto del correo electrónico en la interfaz. |
| **TS-006** | Login con usuario bloqueado | Verificar que un usuario con cuenta bloqueada no pueda acceder al sistema bajo ninguna condición. |

---

# 📝 Casos de Prueba Detallados (Test Cases)

A continuación, se desglosan las instrucciones detalladas paso a paso para ejecutar los escenarios definidos en la tabla anterior.

## 📝 Caso de Prueba para TS-001 (Credenciales Válidas)

| Campo | Detalle |
| --- | --- |
| **Test Case ID** | TC-001 |
| **Test Case Name** | Inicio de sesión con credenciales válidas |
| **Scenario Asociado** | TS-001 (Login con credenciales válidas) |
| **Acceptance Criteria** | El sistema debe permitir el acceso inmediato al Dashboard principal a cualquier usuario que introduzca un correo y contraseña correctos. |
| **Preconditions** | El usuario debe estar registrado previamente en la base de datos y su cuenta debe estar en estado 'Activa'. |
| **Test Data** | Email: usuario.valido@bancopopular.com / Contraseña: ClaveSegura2026! |
| **Steps to Reproduce** | 1. Abrir el navegador e ingresar a la URL. 2. Digitar el correo en el campo Usuario. 3. Digitar la contraseña en el campo Contraseña. 4. Hacer clic en Iniciar Sesión. |
| **Expected Result** | El sistema procesa la autenticación con éxito, redirige a la pantalla de inicio y muestra el mensaje: Bienvenido de nuevo a tu banca en línea. |
| **Actual Result** | El sistema autenticó al usuario correctamente y cargó el Dashboard sin demoras. |
| **Status** | PASS |

---

## 📝 Caso de Prueba para TS-002 (Contraseña Incorrecta)

| Campo | Detalle |
| --- | --- |
| **Test Case ID** | TC-002 |
| **Test Case Name** | Inicio de sesión con contraseña incorrecta |
| **Scenario Asociado** | TS-002 (Login con contraseña incorrecta) |
| **Acceptance Criteria** | El sistema debe denegar el acceso a la plataforma si la contraseña no coincide con el registro de la base de datos, protegiendo la cuenta. |
| **Preconditions** | El usuario debe estar registrado en el sistema. |
| **Test Data** | Email: usuario.valido@bancopopular.com / Contraseña: PasswordEquivocada123 |
| **Steps to Reproduce** | 1. Abrir la aplicación en la pantalla de Login. 2. Introducir el correo electrónico válido del cliente. 3. Introducir una contraseña incorrecta o inventada. 4. Hacer clic en el botón Iniciar Sesión. |
| **Expected Result** | El sistema deniega el acceso, mantiene la pantalla de Login limpia en el campo contraseña y despliega una alerta: Credenciales incorrectas. Por favor, intente de nuevo. |
| **Actual Result** | El acceso fue bloqueado correctamente y se visualizó la alerta roja de credenciales inválidas. |
| **Status** | PASS |

---

## 📝 Caso de Prueba para TS-003 (Correo no Registrado)

| Campo | Detalle |
| --- | --- |
| **Test Case ID** | TC-003 |
| **Test Case Name** | Inicio de sesión con correo no registrado |
| **Scenario Asociado** | TS-003 (Login con correo incorrecto) |
| **Acceptance Criteria** | El sistema debe rechazar el acceso si el correo electrónico ingresado no existe en los registros de la base de datos. |
| **Preconditions** | El usuario se encuentra en la pantalla de Login y el correo a ingresar no debe existir en la BD. |
| **Test Data** | Email: no.existente@bancopopular.com / Contraseña: ClaveCualquiera123 |
| **Steps to Reproduce** | 1. Abrir la aplicación. 2. Digitar el correo electrónico no registrado en el campo de usuario. 3. Digitar cualquier contraseña en el campo correspondiente. 4. Hacer clic en Iniciar Sesión. |
| **Expected Result** | El sistema deniega el acceso y muestra un mensaje de alerta genérico: Credenciales incorrectas o usuario no registrado. |
| **Actual Result** | Acceso denegado con el mensaje de error esperado en la interfaz. |
| **Status** | PASS |

---

## 📝 Caso de Prueba para TS-004 (Campos Obligatorios Vacíos)

| Campo | Detalle |
| --- | --- |
| **Test Case ID** | TC-004 |
| **Test Case Name** | Validación de campos obligatorios vacíos |
| **Scenario Asociado** | TS-004 (Login con campos vacíos) |
| **Acceptance Criteria** | El sistema no debe permitir procesar la solicitud si los campos requeridos se envían en blanco. |
| **Preconditions** | El usuario está en la pantalla de Login. |
| **Test Data** | Email: [Vacío] / Contraseña: [Vacío] |
| **Steps to Reproduce** | 1. Abrir la aplicación. 2. Dejar el campo Usuario completamente vacío. 3. Dejar el campo Contraseña completamente vacío. 4. Hacer clic en el botón Iniciar Sesión. |
| **Expected Result** | El sistema bloquea el envío, resalta los bordes en color rojo y despliega el mensaje inferior: Este campo es obligatorio. |
| **Actual Result** | El formulario fue bloqueado en el cliente y aparecieron las alertas visuales correspondientes. |
| **Status** | PASS |

---

## 📝 Caso de Prueba para TS-005 (Formato de Correo Inválido)

| Campo | Detalle |
| --- | --- |
| **Test Case ID** | TC-005 |
| **Test Case Name** | Validación de formato de correo electrónico inválido |
| **Scenario Asociado** | TS-005 (Login con formato de correo inválido) |
| **Acceptance Criteria** | La interfaz debe validar la estructura del correo electrónico antes de enviar la petición al servidor. |
| **Preconditions** | El usuario está en la pantalla de Login. |
| **Test Data** | Email: ://bancopopular.com / Contraseña: Clave1234! |
| **Steps to Reproduce** | 1. Abrir la aplicación. 2. Digitar un texto sin formato de correo válido en el campo Usuario. 3. Digitar una contraseña válida. 4. Hacer clic en Iniciar Sesión. |
| **Expected Result** | El sistema impide el envío de la solicitud y muestra la alerta de formato: Por favor, introduce una dirección de correo electrónico válida. |
| **Actual Result** | El sistema detectó la falta del formato correcto y lanzó la advertencia visual. |
| **Status** | PASS |

---

## 📝 Caso de Prueba para TS-006 (Usuario Bloqueado)

| Campo | Detalle |
| --- | --- |
| **Test Case ID** | TC-006 |
| **Test Case Name** | Intento de inicio de sesión con una cuenta bloqueada |
| **Scenario Asociado** | TS-006 (Login con usuario bloqueado) |
| **Acceptance Criteria** | El sistema debe denegar el acceso inmediatamente a cualquier cuenta cuyo estado figure como Bloqueada o Inactiva en la base de datos. |
| **Preconditions** | El usuario debe estar registrado, pero su cuenta fue previamente bloqueada debido a políticas de seguridad. |
| **Test Data** | Email: cuenta.bloqueada@bancopopular.com / Contraseña: ClaveSegura2026! |
| **Steps to Reproduce** | 1. Abrir la aplicación. 2. Ingresar el correo de la cuenta bloqueada. 3. Ingresar la contraseña correcta asociada a esa cuenta. 4. Hacer clic en Iniciar Sesión. |
| **Expected Result** | El servidor rechaza la autenticación a pesar de tener la clave correcta y muestra el mensaje: Tu cuenta se encuentra bloqueada temporalmente. Contacta a soporte técnico. |
| **Actual Result** | Acceso restringido por estado de cuenta y mensaje de seguridad desplegado con éxito. |
| **Status** | PASS |
