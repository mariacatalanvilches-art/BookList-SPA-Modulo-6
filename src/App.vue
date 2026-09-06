<template>
  <div id="app-container">
    <header class="app-header">
      <div class="container header-content">
        <div>
          <h1>📚 BookList</h1>
          <p>Gestor interactivo de libros</p>
        </div>

        <nav class="main-nav">
          <RouterLink to="/">Inicio</RouterLink>
          <RouterLink to="/libros">Libros</RouterLink>
        </nav>
      </div>
    </header>

    <main class="container main-content">
      <RouterView />
    </main>

    <footer class="app-footer">
      <p>BookList SPA · Proyecto Módulo 6 · Vue.js</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>