# BookList SPA – Proyecto Módulo 6

Aplicación SPA desarrollada con Vue.js para gestionar un catálogo interactivo de libros.

## Tecnologías

- Vue.js 3
- Vue Router 4
- Vite
- HTML5
- CSS3

## Funcionalidades

- Vista de inicio con nombre de usuario reactivo.
- Contador/listado de libros.
- Formulario con `v-model`.
- Vista previa de los datos ingresados en tiempo real.
- Alta de libros.
- Eliminación de libros.
- Directivas `v-if`, `v-show`, `v-for` y `v-bind` mediante bindings de atributos.
- Eventos `@click`.
- Modificadores `@submit.prevent` y `@click.once`.
- Navegación con Vue Router.
- Ruta dinámica `/libros/:id`.
- Componentes reutilizables.

## Instalación

Tener Node.js instalado. Desde la carpeta del proyecto ejecutar:

```bash
npm install
npm run dev
```

Luego abrir la dirección local indicada por Vite.

Para generar una versión de producción:

```bash
npm run build
```

## Estructura

```text
BookList-SPA/
├── index.html
├── package.json
├── vite.config.js
├── README.md
└── src/
    ├── App.vue
    ├── main.js
    ├── assets/
    │   └── styles.css
    ├── components/
    │   ├── FormularioLibro.vue
    │   └── Libro.vue
    ├── router/
    │   └── index.js
    └── views/
        ├── InicioView.vue
        ├── ListaLibros.vue
        └── DetalleLibro.vue
```

## Relación con las 5 lecciones

### Lección 1
`App.vue` utiliza la estructura de componente Vue y la aplicación incorpora datos reactivos para mostrar el nombre del usuario.

### Lección 2
`Libro.vue` representa los datos mediante props y bindings. La lista utiliza `v-for`, el mensaje de catálogo vacío utiliza `v-if` y la vista previa utiliza `v-show`.

### Lección 3
`FormularioLibro.vue` utiliza `v-model` en inputs, select y textarea. La vista previa muestra los datos ingresados en tiempo real.

### Lección 4
Se utilizan eventos para agregar y eliminar libros. El formulario usa `@submit.prevent`, el botón usa `@click.once` y el botón de envío permite agregar el registro mediante Enter.

### Lección 5
`router/index.js` define `/`, `/libros` y `/libros/:id`. La última es una ruta dinámica que recibe el ID como prop.

## Patrón MVVM

La aplicación separa la interfaz (Views/Components), el estado reactivo y la lógica de interacción mediante componentes Vue. El usuario modifica el modelo a través de `v-model` y Vue actualiza automáticamente la vista.

## Nota

Los datos se mantienen en memoria durante la ejecución de la aplicación. Al recargar el navegador, vuelven los tres libros de ejemplo. Para una versión productiva se podría incorporar una API o almacenamiento persistente.
