```markdown
# Koala Platformer Game

![Koala Platformer](screenshot.png) <!-- Puedes agregar una captura de pantalla del juego aquí -->

Un juego de plataformas simple inspirado en Super Mario Bros, desarrollado utilizando el framework **LibGDX**. El jugador controla un koala que debe navegar a través de niveles llenos de obstáculos y plataformas, saltando y destruyendo bloques para avanzar.

---

## Características

- **Múltiples niveles**: El juego incluye dos niveles (con posibilidad de agregar más).
- **Colisiones y física básica**: Detección de colisiones con bloques y gravedad simulada.
- **Animaciones**: El koala tiene animaciones para caminar, saltar y estar quieto.
- **Mapas personalizados**: Los niveles se crean utilizando **Tiled Map Editor**.
- **Modo de depuración**: Activa/desactiva el modo de depuración para ver hitboxes y tiles.

---

## Requisitos

- **Java JDK 8 o superior**.
- **Gradle** (para compilar y ejecutar el proyecto).
- **Tiled Map Editor** (opcional, para modificar o crear nuevos niveles).

---

## Cómo ejecutar el juego

1. **Clona el repositorio**:
   ```bash
   git clone https://github.com/tu-usuario/koala-platformer.git
   cd koala-platformer
   ```

2. **Compila y ejecuta el juego**:
   - Usando Gradle:
     ```bash
     ./gradlew desktop:run
     ```
   - O importa el proyecto en tu IDE favorito (IntelliJ IDEA, Eclipse, etc.) y ejecuta la clase `Main` en el módulo `desktop`.

3. **Controles**:
   - **Teclado**:
     - `Flecha izquierda` o `A`: Mover a la izquierda.
     - `Flecha derecha` o `D`: Mover a la derecha.
     - `Espacio`: Saltar.
     - `B`: Activar/desactivar modo de depuración.
   - **Pantalla táctil** (si se ejecuta en un dispositivo móvil):
     - Toque en la parte izquierda de la pantalla: Mover a la izquierda.
     - Toque en la parte derecha de la pantalla: Mover a la derecha.
     - Toque en el centro de la pantalla: Saltar.

---

## Estructura del proyecto

- **`core/src/io/github/some_example_name/`**: Contiene la lógica principal del juego.
  - `Main.java`: Clase principal del juego.
  - `Koala.java`: Clase que representa al personaje principal.
- **`assets/`**: Contiene los recursos del juego.
  - `koalio.png`: Spritesheet del koala.
  - `level1.tmx` y `level2.tmx`: Mapas de los niveles creados con Tiled.
- **`desktop/`**: Módulo para ejecutar el juego en escritorio.

---

## Cómo agregar nuevos niveles

1. Abre **Tiled Map Editor** y crea un nuevo mapa con las mismas dimensiones y propiedades que `level1.tmx`.
2. Guarda el archivo en la carpeta `assets/` con un nombre como `level3.tmx`.
3. Modifica el método `loadLevel` en `Main.java` para cargar el nuevo nivel:
   ```java
   private void loadLevel(int level) {
       if (level == 1) {
           map = new TmxMapLoader().load("level1.tmx");
       } else if (level == 2) {
           map = new TmxMapLoader().load("level2.tmx");
       } else if (level == 3) {
           map = new TmxMapLoader().load("level3.tmx");
       }
       renderer = new OrthogonalTiledMapRenderer(map, 1 / 16f);
       koala = new Koala();
       koala.position.set(20, 20); // Reinicia la posición del koala
   }
   ```
4. Ajusta la lógica de transición entre niveles en `updateKoala` si es necesario.

---

## Créditos

- **Sprites y tileset**: [Vicky Wenderlich](http://www.vickiwenderlich.com/).
- **LibGDX**: Framework de desarrollo de juegos en Java.
- **Tiled Map Editor**: Herramienta para crear mapas personalizados.

---

## Licencia

Este proyecto está bajo la licencia **MIT**. Siéntete libre de usarlo, modificarlo y distribuirlo según tus necesidades.

---

¡Diviértete jugando y desarrollando! 🎮
```

### Instrucciones adicionales:
1. **Captura de pantalla**: Agrega una captura de pantalla del juego en la carpeta del proyecto y actualiza la ruta en el archivo `README.md`.
2. **Personalización**: Modifica el contenido del `README.md` para que se ajuste a tu proyecto, como el nombre del repositorio, los créditos o las licencias.
3. **Publicación**: Si subes el proyecto a GitHub, este archivo `README.md` será la página principal de tu repositorio.

¡Espero que este `README.md` sea útil para documentar tu proyecto! 😊
