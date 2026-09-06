<template>
  <section class="hero">
    <div class="hero-content">
      <span class="eyebrow">Editorial Nova</span>
      <h2>Bienvenido a <span>BookList</span></h2>
      <p>
        Una SPA desarrollada con Vue.js para registrar, consultar y administrar
        un catálogo de libros de manera rápida e interactiva.
      </p>

      <div class="welcome-card">
        <label for="usuario">Nombre de usuario</label>
        <input id="usuario" v-model="usuario" type="text" placeholder="Escribe tu nombre" />
        <p v-if="usuario">
          ¡Hola, <strong>{{ usuario }}</strong>! 👋
        </p>
        <p v-else>
          Ingresa tu nombre para personalizar el saludo.
        </p>
      </div>

      <RouterLink class="btn btn-primary" to="/libros">
        Administrar libros →
      </RouterLink>
    </div>

    <div class="hero-book">📚</div>
  </section>

  <section class="features">
    <div class="feature-card">
      <span>⚡</span>
      <h3>Reactivo</h3>
      <p>Los datos se actualizan inmediatamente mediante el sistema reactivo de Vue.</p>
    </div>

    <div class="feature-card">
      <span>🧩</span>
      <h3>Modular</h3>
      <p>Los componentes se separan para facilitar la reutilización y mantenimiento.</p>
    </div>

    <div class="feature-card">
      <span>🧭</span>
      <h3>Navegable</h3>
      <p>Vue Router permite recorrer inicio, catálogo y detalles mediante rutas dinámicas.</p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'InicioView',

  data() {
    return {
      usuario: ''
    }
  }
}
</script>