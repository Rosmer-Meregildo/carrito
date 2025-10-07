# Juego de Carreras (carrito)

Un minijuego de carreras en 2D sobre `canvas`, optimizado para escritorio y móvil. Mueve tu auto entre carriles, esquiva el tráfico y acumula puntos mientras la velocidad aumenta progresivamente. Incluye HUD con Puntos, Mejor puntuación, Velocidad, Tráfico y FPS, además de overlays de Inicio, Ajustes y Game Over.

## Características
- **Controles duales**: teclado (← →, `P` pausa, `R` reiniciar) y botones táctiles en pantalla.
- **Personalización**: nombre del piloto, color del auto y modelo (`Deportivo`, `Sedán`, `Compacto`).
- **Progresión de dificultad**: incremento de velocidad, densidad de tráfico dinámica y separación segura por carril.
- **Gráficos**: vehículos con gradientes, luces, sombras y etiqueta con el nombre del jugador; carretera con líneas animadas.
- **Persistencia local**: mejores puntajes y ajustes guardados en `localStorage`.
- **Responsive y accesible**: se adapta al tamaño de pantalla, `aria-labels` y `aria-live` para HUD.

## Cómo jugar
1. Abre `index.html` en tu navegador.
2. En la pantalla de inicio, opcionalmente define tu nombre, el color del auto y el modelo.
3. Pulsa "Jugar" o toca el `canvas` para comenzar.
4. Evita chocar con los autos del tráfico. La partida termina al primer choque.

## Controles
- **Teclado (PC)**:
  - Izquierda: `←` o `A`
  - Derecha: `→` o `D`
  - Pausa/Reanudar: `P`
  - Reiniciar: `R`
- **Móvil**: usa los botones táctiles de izquierda, pausa y derecha en la barra inferior.

## Personalización en juego
Desde Inicio o en **Ajustes** puedes cambiar:
- **Nombre del piloto** (máx. 16 caracteres)
- **Color del auto** (selector de color)
- **Modelo**: `Deportivo`, `Sedán`, `Compacto` (afectan relación de aspecto y aceleración lateral)

Los cambios se guardan automáticamente y se aplican al vehículo del jugador.

## Persistencia (localStorage)
- Ajustes: clave `racer.settings.v2` con `{ color, model, name }`.
- Mejor puntuación: clave `racer.best.v1` con un número entero.

## Ejecutar localmente
No requiere servidor ni dependencias.
- Opción rápida: doble clic en `index.html`.
- Opción recomendada: servir con un servidor estático para evitar restricciones del navegador (por ejemplo, con VS Code Live Server, `python -m http.server`, o cualquier servidor básico).

## Detalles técnicos
- Render en `canvas 2D` con escalado por `devicePixelRatio` (hasta 3x) y transformación para nitidez en pantallas HiDPI.
- Bucle de juego con `requestAnimationFrame`, temporización `dt` con límite, y contador de FPS.
- Gestión de tráfico por carril con separación mínima dinámica y ventana de seguridad alrededor del jugador para evitar bloqueos inevitables.
- Detección de colisiones AABB y progreso de puntuación basado en velocidad y tiempo.
- Interfaz: HUD con `pointer-events` gestionados para interacción táctil, overlays controlados por clases (`hidden`).

## Accesibilidad y UX
- `aria-label` en elementos interactivos y HUD con `aria-live="polite"`.
- Botones táctiles grandes con feedback visual y sin resalte táctil intrusivo.
- Esquema de color adaptativo (soporta `prefers-color-scheme`).

## Créditos y Licencia
- Autor: Tú
- Licencia: MIT (ajústalo según lo que prefieras)

---
Sugerencias o mejoras son bienvenidas. ¡Diviértete compitiendo!