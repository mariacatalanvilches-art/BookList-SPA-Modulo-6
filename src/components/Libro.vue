<template>
  <article class="book-card">
    <div class="book-icon">📖</div>

    <div class="book-info">
      <span class="category-badge">{{ categoria }}</span>
      <h3>{{ titulo }}</h3>
      <p><strong>Autor:</strong> {{ autor }}</p>
    </div>

    <div class="book-actions">
      <RouterLink
        class="btn btn-secondary"
        :to="{ name: 'detalle-libro', params: { id: id } }"
      >
        Ver detalle
      </RouterLink>

      <button
        type="button"
        class="btn btn-danger"
        @click="$emit('eliminar', id)"
      >
        Eliminar
      </button>
    </div>
  </article>
</template>

<script>
export default {
  name: 'Libro',
  props: {
    id: {
      type: Number,
      required: true
    },
    titulo: {
      type: String,
      required: true
    },
    autor: {
      type: String,
      required: true
    },
    categoria: {
      type: String,
      required: true
    }
  },
  emits: ['eliminar']
}
</script>