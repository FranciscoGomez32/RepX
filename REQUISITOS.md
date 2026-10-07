REQUISITOS DE REPX
==================
Aplicación web de seguimiento de entrenamientos de gimnasio.
Autores: Francisco Gómez Rodríguez y Carlos Mallo Ruiz - IES Trassierra

1. REQUISITOS IMPRESCINDIBLES (MVP)
-----------------------------------
Usuarios
- Registrarse con nombre, correo y contraseña.
- Iniciar y cerrar sesión.

Perfil
- Ver y editar el perfil: altura, peso y objetivo.

Ejercicios
- Catálogo de ejercicios organizado por grupo muscular.
- Cada ejercicio muestra los músculos que trabaja.
- Cada ejercicio tiene una foto (puesta por nosotros al crear el catálogo).

Rutinas
- Crear una rutina con nombre, ejercicios, series y repeticiones.
- Ver, editar y borrar mis rutinas.

Entrenamientos realizados
- Registrar un entrenamiento con fecha, ejercicios, y repeticiones y peso de cada serie.
- Poder partir de una rutina guardada o empezar desde cero.
- Lo que no se apunta no cuenta (no hay que marcar series como no realizadas).
- Ver el historial de entrenamientos.

Requisitos del centro
- Ayuda general y contextual en situaciones críticas.
- Opción "Acerca de..." con nuestros nombres y el IES Trassierra.
- Validación de los datos en todos los formularios.
- Interfaz accesible (WCAG 2.0).
- Separación clara entre Back-end y Front-end.

2. REQUISITOS DESEABLES
-----------------------
- Resumen de cada entrenamiento: ejercicios y series totales.
- Gráfica de barras con el músculo más entrenado ese día.
- Estadísticas semanales en el perfil.
- Biografía en el perfil.

3. EXTRAS (solo si sobra tiempo)
--------------------------------
- Modo oscuro.
- Foto de perfil.
- Gráfica de progreso por ejercicio.
- Historial de peso corporal.

4. DECISIONES TOMADAS
---------------------
- Las estadísticas se calculan con los entrenamientos realizados, no con las rutinas.
- Las fotos de los ejercicios las ponemos nosotros (guardamos solo la ruta de la imagen).

5. PENDIENTE DE DECIDIR
-----------------------
- ¿Los usuarios pueden crear ejercicios propios o solo existe nuestro catálogo?
- ¿El objetivo es una lista de opciones o texto libre?