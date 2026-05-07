Changelog:
    Se ha implementado un sistema de seguimiento para medir el rendimiento del jugador a lo largo de la partida, resolviendo así uno de los ejercicios propuestos en la versión original. A continuación, se detallan los cambios técnicos:

Nuevas Funcionalidades
- Contador de Movimientos: Se introdujo una nueva variable de estado ('taps': 0) dentro del diccionario global state. Esta variable registra la cantidad de veces que el jugador interactúa con el tablero.

- Interfaz de Usuario en Tiempo Real: Se añadió un bloque de renderizado en la función draw() que dibuja un contador de texto (Taps: X) en la esquina superior izquierda de la pantalla, actualizándose constantemente a medida que avanza el juego.

Ajustes en la Lógica
- Captura de Eventos de Clic: Dentro de la función tap(x, y), se agregó un incremento directo al estado del contador (state['taps'] += 1). Ahora, cada vez que la función detecta una pulsación en la pantalla, independientemente de si se descubre un par o no, el movimiento queda registrado.