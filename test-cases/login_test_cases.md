# Login - Test Cases

## TC-001 - Login con credenciales válidas

| Campo | Detalle |
|---|---|
| Test Case ID | TC-001 |
| Test Case | Login con credenciales válidas |
| Acceptance Criteria | El sistema debe permitir el acceso a un usuario registrado que introduzca credenciales válidas. |
| Preconditions | El usuario debe estar registrado y activo. La aplicación debe estar disponible. |
| Test Data | Email: `usuario@email.com` / Contraseña: `Password123` |
| Steps | 1. Abrir la aplicación. 2. Ir a la pantalla de Login. 3. Introducir el email válido. 4. Introducir la contraseña válida. 5. Hacer clic en "Iniciar sesión". |
| Expected Result | El usuario debe iniciar sesión correctamente y acceder a su cuenta. |
| Actual Result | El usuario inició sesión correctamente y accedió a su cuenta. |
| Status | PASS |


## TC-002 - Login con contraseña incorrecta

|---|---|
| **Test Case ID** | TC-002 |
| **Test Case** | Login con contraseña incorrecta |
| **Acceptance Criteria** | El sistema debe denegar el acceso a un usuario registrado si introduce una contraseña incorrecta y mostrar un mensaje de error claro. |
| **Preconditions** | El usuario debe estar registrado y activo. La aplicación debe estar disponible. |
| **Test Data** | Email: `usuario@email.com` / Contraseña: `PasswordErrada123` |
| **Steps** | 1. Abrir la aplicación.<br>2. Ir a la pantalla de Login.<br>3. Introducir el email válido.<br>4. Introducir la contraseña incorrecta.<br>5. Hacer clic en "Iniciar sesión". |
| **Expected Result** | El sistema debe rechazar el acceso, no permitir el ingreso y mostrar el mensaje: *"Credenciales incorrectas. Intente de nuevo"*. |
| **Actual Result** | El sistema rechazó el acceso correctamente y mostró el mensaje de error esperado. |
| **Status** | PASS |


## TC-003 - Validación de campos obligatorios vacíos

| :--- | :--- |
| **Test Case ID** | TC-003 |
| **Test Case** | Validación de campos obligatorios vacíos |
| **Acceptance Criteria** | El sistema no debe permitir el envío del formulario si los campos obligatorios (Email y Contraseña) se encuentran vacíos. |
| **Preconditions** | La aplicación debe estar disponible y el usuario en la pantalla de Login. |
| **Test Data** | Email: `[Vacío]` / Contraseña: `[Vacío]` |
| **Steps** | 1. Abrir la aplicación.<br>2. Ir a la pantalla de Login.<br>3. Dejar el campo de email completamente vacío.<br>4. Dejar el campo de contraseña completamente vacío.<br>5. Hacer clic en "Iniciar sesión". |
| **Expected Result** | El sistema no debe realizar la petición de login, debe resaltar ambos campos en rojo y mostrar el mensaje de alerta debajo de cada uno: *"Este campo es obligatorio"*. |
| **Actual Result** | Los campos se marcaron en rojo con sus respectivas alertas de validación bloqueando el envío. |
| **Status** | PASS |


## TC-004 - Bloqueo de cuenta por intentos fallidos

| :--- | :--- |
| **Test Case ID** | TC-004 |
| **Test Case** | Bloqueo de cuenta por intentos fallidos |
| **Acceptance Criteria** | Por motivos de seguridad, el sistema debe bloquear temporalmente la cuenta del usuario tras 3 intentos consecutivos fallidos de inicio de sesión. |
| **Preconditions** | El usuario debe estar registrado y activo. La aplicación debe estar disponible. |
| **Test Data** | Email: `usuario@email.com` / Contraseña: `ClaveInvalidaXYZ` |
| **Steps** | 1. Abrir la aplicación e ir a la pantalla de Login.<br>2. Introducir el email y una contraseña incorrecta; hacer clic en "Iniciar sesión" (Intento 1).<br>3. Repetir el paso anterior con contraseña incorrecta (Intento 2).<br>4. Repetir el paso anterior con contraseña incorrecta (Intento 3).<br>5. Intentar ingresar una cuarta vez con las credenciales correctas. |
| **Expected Result** | En el cuarto intento el sistema debe denegar el acceso (incluso si la clave es correcta) y mostrar un mensaje indicando que la cuenta ha sido bloqueada temporalmente por 15 minutos debido a actividad sospechosa. |
| **Actual Result** | La cuenta se bloqueó de forma exitosa tras el tercer intento fallido lanzando la advertencia temporal en pantalla. |
| **Status** | PASS |
