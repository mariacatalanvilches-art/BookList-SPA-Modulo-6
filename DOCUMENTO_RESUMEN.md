# Documento resumen – BookList SPA

## 1. Identificación del proyecto

**Nombre:** BookList SPA – Gestor Interactivo de Libros  
**Módulo:** 6 – Desarrollo de Interfaces Interactivas con Framework Vue  
**Unidad solicitante:** Área de Desarrollo Frontend – Editorial Nova  
**Repositorio GitHub:** https://github.com/mariacatalanvilches-art/BookList-SPA-Modulo-6

## 2. Objetivo

Desarrollar una Single Page Application utilizando Vue.js que permita gestionar un catálogo de libros mediante una interfaz interactiva, modular y de fácil navegación.

## 3. Funcionalidades implementadas

La aplicación permite:

- Ingresar título, autor, categoría y descripción de un libro.
- Actualizar los datos del formulario en tiempo real.
- Visualizar una vista previa mientras se escribe.
- Agregar libros al catálogo.
- Eliminar libros.
- Mostrar un mensaje cuando no existen libros.
- Navegar entre Inicio, Lista de libros y Detalle del libro.
- Consultar un libro mediante una ruta dinámica.
- Mostrar un saludo personalizado mediante el nombre de usuario.

## 4. Desarrollo según las lecciones

### Lección 1 – Introducción a Vue.js

Se implementó `App.vue` como componente principal. La vista de inicio contiene un campo vinculado al dato reactivo `usuario`, demostrando la comunicación entre modelo y vista propia del patrón MVVM.

### Lección 2 – Templates y rendering

Se creó el componente reutilizable `Libro.vue`, que recibe información mediante props. Se emplean directivas de Vue como:

- `v-for` para recorrer el catálogo.
- `v-if` para mostrar el catálogo o el mensaje de ausencia de libros.
- `v-show` para controlar la vista previa del formulario.
- `v-bind` mediante bindings dinámicos en enlaces y propiedades de componentes.

### Lección 3 – Binding de formularios

`FormularioLibro.vue` utiliza `v-model` en campos de texto, selección y área de texto. Los datos ingresados se reflejan inmediatamente en la vista previa.

### Lección 4 – Manejo de eventos

Se utilizan eventos `@click` para las acciones del catálogo. También se incorpora `@submit.prevent` para evitar el envío tradicional del formulario y `@click.once` como ejemplo de modificador de evento. Al presionar Enter en el formulario se ejecuta el evento submit y se registra el libro.

### Lección 5 – Manejo de rutas

Se configuró Vue Router con las siguientes rutas:

- `/` → Inicio.
- `/libros` → Lista de libros.
- `/libros/:id` → Detalle dinámico.

La ruta de detalle utiliza `props: true` para recibir el identificador del libro como propiedad.

## 5. Modularidad

La solución está separada en:

- `App.vue`: estructura general y navegación.
- `FormularioLibro.vue`: formulario reutilizable.
- `Libro.vue`: representación reutilizable de cada libro.
- `InicioView.vue`: pantalla principal.
- `ListaLibros.vue`: gestión del catálogo.
- `DetalleLibro.vue`: detalle de un libro.
- `router/index.js`: configuración de rutas.

Esta organización facilita el mantenimiento y permite ampliar la aplicación en el futuro.

## 6. Decisiones de diseño

Se escogió una interfaz limpia y responsive para que la aplicación pueda utilizarse tanto en computadores como en dispositivos móviles. Se utilizaron tarjetas, botones diferenciados y mensajes de estado para facilitar la interacción.

## 7. Persistencia

En esta versión los datos se mantienen en memoria. Esto es suficiente para demostrar los conceptos solicitados en el módulo. Como mejora futura se podría conectar la aplicación a una API REST y una base de datos.

## 8. Conclusión

BookList cumple los requerimientos principales de la evaluación del módulo 6: utiliza componentes Vue, reactividad, formularios con `v-model`, directivas, eventos, componentes reutilizables y Vue Router con rutas dinámicas. La solución queda preparada como prototipo para futuras ampliaciones.

## 9. Evidencias de la entrega

Las capturas de pantalla que respaldan el funcionamiento de la aplicación se encuentran respaldadas y organizadas dentro de la carpeta `/Evidencias` en la raíz del proyecto:

1. Pantalla de Inicio mostrando el nombre de usuario.
2. Formulario de creación de libro con la vista previa activa.
3. Catálogo con varios libros.
4. Catálogo después de eliminar un libro.
5. Página de detalle con una URL similar a `/libros/1`.
6. Vista responsive adaptada a pantallas pequeñas.