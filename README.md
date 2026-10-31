# Mis Cartillas de Bingo

Página web para seguir varias cartillas de bingo (formato americano de 75 bolas, B-I-N-G-O) al mismo tiempo. Escribes el número que cantan y la página te dice al instante en qué cartillas lo tienes, lo marca en todas y te muestra cuál está más cerca de ganar.

Es un solo archivo HTML. No necesita instalación, servidor ni internet.

## Cómo abrirlo

- **En la computadora:** doble clic en `bingo-cartillas.html` y se abre en tu navegador.
- **En el celular:** descarga el archivo y ábrelo con Chrome (u otro navegador) desde Archivos o Descargas.
- **En línea con GitHub Pages:** renombra el archivo a `index.html`, súbelo al repositorio y activa Pages en *Settings → Pages* (rama `main`, carpeta raíz). Te dará un enlace del tipo `https://tu-usuario.github.io/nombre-del-repo/`.

Sin conexión todo funciona igual. Solo cambia la tipografía de los números, que pasa a una fuente del sistema.

## Cómo se usa

### 1. Registrar tus cartillas

En la sección **Agregar cartilla**:

1. Escribe el **número de control** (el que aparece en la casilla central).
2. Llena los 24 números de una de estas dos formas:
   - **Casilla por casilla:** al escribir 2 cifras salta sola a la siguiente. Enter también avanza.
   - **Escritura rápida:** escribe los 24 números seguidos, fila por fila de izquierda a derecha, saltando el centro y separados por espacios. Por ejemplo:
     `7 19 43 51 71 15 25 38 50 63 14 18 57 62 6 24 37 49 70 13 16 36 56 68`
3. Pulsa **Guardar cartilla**.

La página revisa que:

- cada número esté en el rango de su columna (B 1–15, I 16–30, N 31–45, G 46–60, O 61–75),
- no haya números repetidos en la cartilla,
- no repitas un número de control ya registrado.

Cada cartilla se puede **editar** o **eliminar** desde su tarjeta.

### 2. Elegir la modalidad

Arriba, en **Jugando a**, elige qué se juega en esa ronda:

| Modalidad     | Ganas cuando completas…                                |
|---------------|--------------------------------------------------------|
| Línea         | cualquier fila, columna o una de las dos diagonales    |
| 4 esquinas    | las cuatro esquinas de la cartilla                     |
| Cartón lleno  | las 24 casillas                                        |

La casilla central (control) cuenta siempre como marcada.

### 3. Durante el juego

- Escribe el número que cantan (`43` o `N43`, da igual) y pulsa **Enter** o **Cantar**.
- También puedes tocar el número en el **Tablero 1–75**.

Al cantar un número:

- Arriba aparece si lo tienes y en qué cartillas (por número de control), o si no está en ninguna.
- Se marca en todas tus cartillas, y la última casilla marcada queda resaltada.
- Las cartillas se **ordenan solas**, de la más cercana a ganar a la más lejana.
- Si a una cartilla le faltan 1 o 2 números, te dice exactamente cuáles necesitas.
- Cuando una completa la figura, aparece **¡BINGO!** en verde.

Otros controles:

- **Deshacer último:** quita el último número cantado, por si te equivocaste.
- **Nuevo juego:** borra los números cantados (pide confirmación). Tus cartillas no se borran.
- El tablero 1–75 distingue los números que ya salieron, los que salieron y tienes, y los que están en tus cartillas.

## Dónde se guardan los datos

Todo se guarda **automáticamente** cada vez que agregas, editas o borras una cartilla, cantas un número, deshaces o cambias de modalidad. No hay botón de guardar.

Los datos **no se guardan dentro del archivo HTML**. Se guardan en el almacenamiento local del navegador (`localStorage`). Eso significa:

- Si cierras y vuelves a abrir la página en el **mismo navegador y dispositivo**, todo sigue ahí.
- Si abres el archivo en **otro navegador, otro dispositivo o en modo incógnito**, empieza de cero (con las cartillas de ejemplo).
- Si **borras los datos de navegación** del sitio, se pierden las cartillas registradas.
- El archivo abierto localmente, la versión en GitHub Pages y cualquier otra copia guardan sus datos **por separado**, porque el navegador los trata como sitios distintos.

Consejo: registra las cartillas en el mismo celular y navegador que vas a usar en el bingo.

## Cartillas de ejemplo

La primera vez que se abre, la página trae cargadas unas cartillas de ejemplo (controles 3547, 3548, 3550, 3551 y 3552). Puedes eliminarlas desde su tarjeta, o editar la lista `seed` dentro del `<script>` del HTML para que vengan otras (o ninguna) por defecto.

## Detalles técnicos

- HTML, CSS y JavaScript puro en un solo archivo, sin librerías.
- Tipografías Anton y Barlow de Google Fonts, con fuentes del sistema como respaldo.
- Se adapta a celular y tiene modo claro y oscuro según la configuración del dispositivo.
- Los datos se guardan en `localStorage` bajo la clave `bingo-cartillas-v1`.
