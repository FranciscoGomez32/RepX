# Casos de uso de RepX

## CasoDeUso-01: Registrarse

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

## CU-03: Crear rutina

**Actor:** Usuario

**Descripción:** El usuario crea una rutina de entrenamiento con un nombre y una lista de ejercicios, indicando las series y repeticiones previstas de cada uno.

**Precondición:** El usuario tiene la sesión iniciada.

**Flujo principal:**

1. El usuario pulsa "Crear rutina".
2. Escribe el nombre de la rutina (por ejemplo, "Pecho y tríceps").
3. Añade un ejercicio eligiéndolo del catálogo, que puede filtrar por grupo muscular.
4. Indica las series y las repeticiones previstas para ese ejercicio.
5. Repite los pasos 3 y 4 para añadir más ejercicios.
6. Pulsa "Guardar".
7. El sistema valida los datos, guarda la rutina y la muestra en la lista de rutinas del usuario.

**Flujos alternativos:**

- 7a. El nombre está vacío: el sistema muestra el error y no guarda la rutina.
- 7b. La rutina no tiene ningún ejercicio: el sistema avisa de que hay que añadir al menos uno y no guarda la rutina.
- 7c. Las series o repeticiones no son números enteros mayores que cero: el sistema muestra el error y no guarda la rutina.
- 5a. El usuario se equivoca al añadir un ejercicio: puede quitarlo de la rutina antes de guardar.
- 6a. El usuario cancela: no se guarda nada y vuelve a la lista de rutinas.

**Postcondición:** La rutina queda guardada en la cuenta del usuario y está disponible para editarla, borrarla o usarla al registrar un entrenamiento.


## CU-04: Registrar entrenamiento

**Actor:** Usuario

**Descripción:** El usuario guarda lo que ha entrenado un día concreto, indicando para cada ejercicio las repeticiones y el peso de cada serie realizada.

**Precondición:** El usuario tiene la sesión iniciada.

**Flujo principal:**

1. El usuario pulsa "Registrar entrenamiento".
2. El sistema propone la fecha de hoy, que el usuario puede cambiar.
3. El usuario añade un ejercicio eligiéndolo del catálogo.
4. Para ese ejercicio, apunta cada serie realizada con sus repeticiones y su peso (kg).
5. Repite los pasos 3 y 4 para añadir más ejercicios.
6. Pulsa "Guardar".
7. El sistema valida los datos, guarda el entrenamiento y lo muestra en el historial.

**Flujos alternativos:**

- 1a. Partir de una rutina (extend): el usuario elige una de sus rutinas y el sistema carga sus ejercicios y series previstas como punto de partida. El usuario modifica los datos con lo que realmente hizo y continúa en el paso 6.
- 4a. El usuario no hizo todas las series previstas: solo apunta las que hizo. Lo que no se apunta no cuenta.
- 5a. El usuario quita un ejercicio que no llegó a hacer: el sistema lo elimina del entrenamiento antes de guardar.
- 7a. La fecha está vacía o es futura: el sistema muestra el error y no guarda.
- 7b. Las repeticiones no son un entero mayor que cero, o el peso es negativo o no es un número: el sistema muestra el error y no guarda.
- 7c. El entrenamiento no tiene ninguna serie: el sistema avisa de que hay que apuntar al menos una y no guarda.
- 6a. El usuario cancela: no se guarda nada y vuelve a la pantalla anterior.

**Postcondición:** El entrenamiento queda guardado en la cuenta del usuario y alimenta el historial y las estadísticas.