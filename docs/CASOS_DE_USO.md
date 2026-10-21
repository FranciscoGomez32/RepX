# Casos de uso de RepX

## CasoDeUso-01: Registrarse

**Nombre** Registrarse 

**Actor:** Usuario

**Descripción:** El usuario crea una cuenta nueva en RepX para poder usar la aplicación.

**Precondición:** El usuario no tiene sesión iniciada.

**Flujo principal:**

1. El usuario abre la página de registro.
2. Introduce nombre, correo y contraseña.
3. El sistema valida los datos.
4. El sistema crea la cuenta y guarda la contraseña cifrada.
5. El sistema inicia la sesión automáticamente y lleva al usuario a la aplicación.

**Flujos alternativos:**

- 3a. Algún dato no es válido (correo mal escrito, contraseña muy corta): el sistema muestra el error y no crea la cuenta.
- 3b. El correo ya está registrado: el sistema avisa y no crea la cuenta.

**Postcondición:** Existe un nuevo usuario en la base de datos y tiene la sesión iniciada.

## CU-02: Iniciar sesión

**Actor:** Usuario

**Descripción:** El usuario accede a su cuenta de RepX con su correo y contraseña para poder usar la aplicación.

**Precondición:** El usuario tiene una cuenta creada y no tiene sesión iniciada.

**Flujo principal:**

1. El usuario abre la página de inicio de sesión.
2. Introduce su correo y su contraseña.
3. El sistema valida que los campos no estén vacíos y tengan un formato correcto.
4. El sistema comprueba que el correo existe y que la contraseña coincide con la guardada (cifrada).
5. El sistema inicia la sesión y lleva al usuario a la aplicación.

**Flujos alternativos:**

- 3a. Algún campo está vacío o el correo tiene un formato incorrecto: el sistema muestra el error y no continúa.
- 4a. El correo no existe o la contraseña es incorrecta: el sistema muestra un mensaje genérico ("Correo o contraseña incorrectos") y no inicia la sesión.

**Postcondición:** El usuario tiene la sesión iniciada y puede acceder a las funciones de la aplicación.