# PocketStore Autos

PocketStore Autos es una PWA desarrollada con HTML, CSS y JavaScript puro. Consume la categoría `vehicle` de la API pública DummyJSON y almacena la información en caché para poder consultar el catálogo sin Internet.

## Funciones

- Catálogo dinámico de automóviles.
- Datos consumidos con `fetch()` desde una API pública.
- Buscador por nombre, marca o descripción.
- Diseño responsive.
- Service Worker con eventos `install`, `activate` y `fetch`.
- App Shell almacenado en caché.
- Datos de la API almacenados para modo offline.
- Caché de imágenes consultadas.
- Manifest para instalación como PWA.

## API utilizada

`https://dummyjson.com/products/category/vehicle`

## Estructura

```text
pocket-store-autos/
├── index.html
├── styles.css
├── app.js
├── sw.js
├── manifest.json
├── README.md
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── images/
```

## Cómo ejecutar

No abras `index.html` directamente con `file://`, ya que el Service Worker requiere localhost o HTTPS.

### Visual Studio Code + Live Server

1. Abre la carpeta `pocket-store-autos` en Visual Studio Code.
2. Instala la extensión **Live Server**.
3. Abre `index.html`.
4. Haz clic derecho y selecciona **Open with Live Server**.
5. Se abrirá una dirección como `http://127.0.0.1:5500/`.

## Cómo probar el modo offline

1. Ejecuta la aplicación con Internet y espera a que los autos e imágenes se carguen.
2. Abre DevTools con F12.
3. Ve a **Application > Service Workers** y confirma que `sw.js` esté activo.
4. Ve a **Network** y selecciona **Offline**.
5. Recarga la página.
6. El App Shell y los autos previamente almacenados deben continuar disponibles.

> Para comprobar también las imágenes offline, deja que las imágenes visibles terminen de cargar antes de desconectarte.

## Estrategias de caché

- **Cache First:** archivos estáticos e imágenes.
- **Network First:** datos del catálogo de vehículos.

## Capturas sugeridas para `/images`

- `01-estructura-proyecto.png`
- `02-catalogo-autos.png`
- `03-api-vehiculos.png`
- `04-service-worker.png`
- `05-cache-storage.png`
- `06-modo-offline.png`
- `07-manifest.png`
