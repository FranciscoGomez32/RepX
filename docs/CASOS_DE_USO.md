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