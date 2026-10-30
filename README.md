# Cannon - Proyecto colaborativo

## Descripción

Este repositorio contiene una adaptación del videojuego Cannon de Free Python Games, desarrollado en Python con Turtle Graphics. El jugador dispara un proyectil para intentar alcanzar los balones que se desplazan por la ventana.

La actividad consiste en aumentar la velocidad del proyectil y de los balones, y permitir que la partida continúe cuando un balón salga de la ventana. El equipo utiliza Git y GitHub para registrar e integrar sus contribuciones.

## Fuente original

Código base de Grant Jenks:

https://grantjenks.com/docs/freegames/cannon.html

El código original se obtiene con:

```bash
python -m freegames copy cannon
```

Este comando se utiliza al preparar el proyecto inicial. Después de clonar el repositorio, no debe ejecutarse nuevamente sobre el archivo modificado.

## Integrantes y roles

| Integrante | Matrícula | Usuario de GitHub | Rol |
|---|---|---|---|
| Yerik Escobar Asprón | A01829079 | Yeaspron | Dueño del repositorio / Main |
| Diego Lemus Mejía | A01665486 | a01665486-debug | Fork |

Cada integrante utiliza su propia cuenta. Diego contribuye desde un fork y envía sus cambios mediante un pull request, sin acceso de colaborador al repositorio original.

## Reparto de funcionalidades

| Responsable | Funcionalidad | Estado |
|---|---|---|
| Yerik | Aumentar la velocidad del proyectil y de los balones | Implementación reportada por el equipo; falta registrar su detalle y validación |
| Diego | Mantener la partida activa y reposicionar los balones que salen de la ventana | Pendiente de confirmar implementación e integración |

### Velocidad: contribución de Yerik

El cambio asignado consiste en acelerar tanto el movimiento del proyectil como el de los balones. Deben registrarse aquí las instrucciones o parámetros efectivamente modificados, sus valores originales y finales, y las pruebas realizadas.

Detalle de la implementación: pendiente de completar con el código de Yerik.

### Partida continua: contribución de Diego

El cambio previsto sustituye la condición que termina la actualización al salir un balón de la ventana. Cuando un balón cruza el borde izquierdo, se reposiciona a la derecha con una altura aleatoria, permitiendo que continúe la partida.

El bloque propuesto para el final de `move()` es:

```python
for target in targets:
    if target.x < -200:
        target.x = 200
        target.y = randrange(-150, 150)
```

Este bloque debe conservar la indentación dentro de `move()` y la programación de la siguiente actualización mediante `ontimer`. `randrange(-150, 150)` selecciona una altura entera entre -150 y 149.

Diego conserva el cambio de velocidad realizado por Yerik. La confirmación del comportamiento conjunto queda pendiente hasta probar la versión integrada.

## Requisitos

- Python 3 con Turtle y Tkinter disponibles.
- Git para administrar versiones.
- FreeGames, instalado dentro de un ambiente virtual.
- En Windows WSL: soporte para aplicaciones gráficas.

## Instalación

Clonar el repositorio correspondiente y entrar a su carpeta. El dueño utiliza su repositorio y Diego utiliza su fork. Copiar la URL real desde GitHub; no introducir espacios en el nombre del repositorio.

Desde esa carpeta, ejecutar en Terminal de macOS o Ubuntu WSL:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install freegames
```

Cada integrante crea su propio ambiente virtual. La carpeta `.venv/` debe estar excluida del control de versiones mediante `.gitignore`.

## Ejecución

Con el ambiente activado:

```bash
python cannon.py
```

En sesiones posteriores, entrar a la carpeta y activar el ambiente antes de ejecutar:

```bash
source .venv/bin/activate
python cannon.py
```

Para salir del ambiente:

```bash
deactivate
```

## Controles

- Clic izquierdo en la ventana: disparar y definir la dirección y fuerza inicial del proyectil según el punto seleccionado.
- Para reiniciar la partida, cerrar la ventana y ejecutar nuevamente el programa.
- Para terminar una partida continua, cerrar la ventana.

## Flujo de colaboración

1. Conservar el código original en el primer commit.
2. Acordar el reparto de funcionalidades antes de programar.
3. Trabajar en ramas separadas y registrar cada funcionalidad en un commit atómico.
4. Documentar los cambios y las pruebas de cada integrante.
5. Subir las ramas y abrir pull requests hacia `main` del repositorio original.
6. Revisar e integrar los cambios conservando los commits y sus autores.
7. Actualizar las copias locales y probar el resultado conjunto.

La rama prevista para Diego es `feat/infinite`. El desarrollo de ambas contribuciones puede realizarse simultáneamente; los conflictos se revisan antes de integrar.

## Pruebas manuales

Los siguientes resultados deben completarse después de ejecutar las pruebas. No representan pruebas aprobadas todavía.

| Prueba | Procedimiento | Resultado esperado | Resultado observado |
|---|---|---|---|
| Inicio | Ejecutar `python cannon.py` | Se abre la ventana sin errores | Pendiente |
| Disparo | Hacer clic en diferentes posiciones | El proyectil se lanza y cambia su trayectoria | Pendiente |
| Velocidad del proyectil | Comparar el original y la versión modificada con condiciones equivalentes | El proyectil se mueve más rápido | Pendiente |
| Velocidad de los balones | Comparar el desplazamiento con el original | Los balones se mueven más rápido | Pendiente |
| Reposición | Dejar pasar un balón sin dispararle | Al cruzar el borde izquierdo reaparece a la derecha | Pendiente |
| Continuidad | Dejar salir varios balones y después disparar | La animación y los disparos continúan | Pendiente |
| Acierto | Alcanzar un balón con el proyectil | Se conserva la detección de impactos | Pendiente |
| Integración | Ejecutar la versión con ambas contribuciones | Mayor velocidad y reposición funcionan juntas | Pendiente |

## Problemas encontrados

Pendiente de registrar los problemas reales de esta actividad, si se presentan. Cada registro debe indicar el síntoma, su causa identificada, la corrección y la comprobación realizada.

## Historial y evidencia

Los commits, pull requests y merges en GitHub documentan las contribuciones individuales. El README se actualiza conforme se implementan y prueban las funcionalidades.

Para consultar el historial:

```bash
git --no-pager log --graph --oneline --all
```

La entrega incluye el código modificado y la historia de commits, conforme a las instrucciones de la actividad. Para la evidencia general, cada integrante presenta su archivo de texto con los datos del equipo, enlaces de los repositorios y enlace a su video individual.
