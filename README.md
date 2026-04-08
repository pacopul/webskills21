# webskills21

## Footer fijo abajo con Flexbox (Bootstrap)

Para conseguir que el footer siempre se sitúe en la parte inferior de la página, incluso cuando el contenido es escaso, se utilizan las siguientes clases de Bootstrap en combinación:

### Clases utilizadas

1. **`d-flex`** — Activa Flexbox en el contenedor principal.
2. **`flex-column`** — Establece la dirección del eje principal en vertical (`flex-direction: column`), de modo que los hijos (navbar, contenido y footer) se apilan de arriba a abajo.
3. **`min-vh-100`** — Fuerza que el contenedor ocupe como mínimo el 100% de la altura del viewport (`min-height: 100vh`). Esto garantiza que la página siempre llene toda la pantalla.
4. **`flex-grow-1`** — Se aplica al bloque central de contenido. Hace que ese elemento crezca para ocupar todo el espacio vertical sobrante (`flex-grow: 1`), empujando así al footer hacia abajo.

### Estructura

```html
<div class="container-fluid p-0 d-flex flex-column min-vh-100">
    <nav>...</nav>              <!-- Navbar: altura automática -->
    <div class="flex-grow-1">   <!-- Contenido: crece para llenar el espacio -->
        ...
    </div>
    <div class="bg-secondary">  <!-- Footer: queda siempre abajo -->
        ...
    </div>
</div>
```

### ¿Por qué funciona?

- El contenedor ocupa al menos toda la pantalla (`min-vh-100`).
- Los hijos se distribuyen en columna (`flex-column`).
- El navbar y el footer solo ocupan la altura que necesitan.
- El contenido central absorbe todo el espacio restante gracias a `flex-grow-1`.
- Si el contenido es corto, el espacio sobrante lo ocupa la zona central y el footer queda pegado al final de la ventana.
- Si el contenido es largo, la página crece más allá del viewport y el footer se coloca naturalmente después del contenido.
