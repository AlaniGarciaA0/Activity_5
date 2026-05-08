Changelog:
    Se han implementado mejoras significativas en la experiencia de usuario y en el ciclo de vida del juego. Se introdujo un sistema de seguimiento para medir el rendimiento del jugador y una condición de victoria para detectar automáticamente la resolución del puzzle.

Nuevas Funcionalidades
- Contador de Movimientos: Se introdujo una nueva variable de estado ('taps': 0) dentro del diccionario global state que registra la cantidad de interacciones del jugador.

- Interfaz de Usuario  en Tiempo Real: Se añadió un contador de texto (Taps: X) en la esquina superior izquierda de la pantalla, que se actualiza constantemente durante la partida.

- Mensaje de Victoria: Se integró un aviso visual que despliega el mensaje "You Win!" en color rojo y formato negrita en el centro de la pantalla cuando se descubren todos los pares.

Ajustes en la Lógica
- Captura de Eventos de Clic: En la función tap(x, y), se agregó un incremento directo al estado del contador (state['taps'] += 1). Cada pulsación en la pantalla queda registrada como un movimiento.

- Validación del Arreglo de Fichas: Dentro de la función draw(), se incorporó la condición if not any(hide): para evaluar la lista booleana de fichas ocultas. Si no queda ningún valor True, se activa la secuencia de finalización.

- Interrupción del Ciclo de Renderizado: Al cumplirse la condición de victoria, la función ejecuta un update() final y un return, interrumpiendo el bucle recursivo ontimer(draw, 100). Esto detiene el procesamiento en segundo plano y optimiza el uso de recursos al concluir la partida.

Mejoras visuales
- Alineacion de los elementos: Se alinearon los elementos para que quedaran centrados dentro de las casillas al alinear el texto a center y modificar las coordenadas X y Y de mark aproximadas al centro, sumándole 25 a X, debido a que la casilla mide 50, y 8 a Y, después de hacer pruebas, se determinó que esa era la cantidad que propiciaba que los elementos quedarán lo mejor centrados posibles.

- Emojis: Se reemplazó la lista de dígitos por una lista de emojis para mejorar la memoria del usuario presentando elementos más atractivos visualmente. Esta fue la lista de emojis utilizada: ['⚽️', '🏆', '🤿🫱', '🎸', '😎', '👻', '🥶', '🐙', '🙉', '🗿', '🍕', '🍦', '⭐️', '☃️', '🏀', '🥸', '🤡', '💀', '🎰', '🔥', '🍍', '⚾️', '🏈', '🎱', '🎮', '🏎️', '🚀', '⁶🤷‍♂️⁷', '🐸', '🌹', '🪩', '🎩']