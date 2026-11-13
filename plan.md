# TallerApp — plan de implementación y diseño

## Alcance
TallerApp será una app web para administrar citas de un taller automotriz, tomando como base el `App.js` y las capturas entregadas. La primera versión tendrá navegación por Inicio, Citas, Nueva cita y Reportes; cargará los 20 registros iniciales entregados, permitirá crear/editar/eliminar citas, filtrar y buscar información, y conservará los cambios en el navegador para una prueba inmediata. La infraestructura administrada con servidor y base de datos queda habilitada en el proyecto para la siguiente iteración de persistencia multi-dispositivo.

## Arquitectura
- `client/src/App.tsx`: estado de navegación, operaciones CRUD, filtros, métricas, reportes y componentes de pantalla.
- `client/src/index.css`: sistema visual responsive y componentes de layout.
- `client/src/data.ts`: datos iniciales extraídos del `App.js` entregado.
- `public/manus-routes.json`: rutas declaradas para Preview y publicación.
- `server/` y `drizzle/`: starter administrado disponible para incorporar endpoints y tabla de citas sin cambiar el flujo visual.

## Diseño
### Estilos considerados
- **Taller nocturno premium** — 0.06: oscuro, preciso y con naranja de señalización como color de acción.
- **Panel industrial claro** — 0.04: superficies grises y jerarquía tipo sistema operativo.
- **Garage retro** — 0.02: alto contraste, texturas y acentos de neón.

Se elige **Panel iOS claro**, porque conserva la personalidad de TallerApp pero reduce la fatiga visual y se siente más elegante, familiar y ligero en pantallas grandes y pequeñas.

- **Movimiento:** dashboard automotriz contemporáneo, con superficies blancas, sombras suaves, bordes redondeados y acciones coral de alta visibilidad.
- **Principios:** lectura rápida, acciones primarias obvias, densidad controlada, claridad visual y adaptación mobile-first.
- **Color:** gris perla para el lienzo, blanco para las superficies, azul grafito para el texto y coral `#ff7043` como color propio de TallerApp para acciones y estados activos.
- **Layout:** rail lateral en escritorio y navegación inferior fija en móvil; el contenido usa una columna principal ancha con paneles asimétricos y tarjetas de agenda.
- **Firma visual:** marca coral con llave inglesa, chips suaves de fecha/servicio y tarjetas blancas con una línea de estado lateral.
- **Interacción:** cada acción CRUD confirma el cambio en el contexto; editar reutiliza el formulario; eliminar exige confirmación y las búsquedas actualizan el listado al instante.
- **Animación:** entradas suaves de paneles, hover elevado en tarjetas, botones con feedback corto; sin animaciones que retrasen la agenda.
- **Tipografía:** Inter/system sans para lectura de datos, títulos en peso 800 y números de métricas con tracking compacto.
- **Esencia:** “la agenda del taller, clara a primera vista”; directa, confiable, práctica.
- **Voz:** CTAs como “Nueva cita” y “Guardar cambios”; microcopy como “Todo bajo control” y “Encuentra una cita en segundos”.
- **Wordmark:** icono llave inglesa dentro de un círculo naranja junto a “TallerApp”; no depende de una imagen externa.
- **Color de marca:** coral `#ff7043`.

## Persistencia y evolución
La versión entregada guarda cambios en `localStorage` para que crear, editar y eliminar sean funcionales en Preview de inmediato. La base de datos administrada queda habilitada y la estructura del starter se conserva para migrar estas mismas operaciones a Drizzle/tRPC en la siguiente fase, evitando bloquear la revisión visual y de interacción.
