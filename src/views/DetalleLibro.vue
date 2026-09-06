<template>
  <section>
    <RouterLink class="back-link" to="/libros">← Volver al catálogo</RouterLink>

    <div v-if="libro" class="detail-card">
      <div class="detail-icon">📖</div>

      <div class="detail-content">
        <span class="category-badge">{{ libro.categoria }}</span>
        <h2>{{ libro.titulo }}</h2>
        <p class="author"><strong>Autor:</strong> {{ libro.autor }}</p>

        <div class="description">
          <h3>Descripción</h3>
          <p>{{ libro.descripcion || 'No se ingresó una descripción para este libro.' }}</p>
        </div>

        <p class="route-info">
          ID del libro: <strong>{{ id }}</strong>
        </p>
      </div>
    </div>

    <div v-else class="empty-state">
      <span>🔎</span>
      <h3>Libro no encontrado</h3>
      <p>El libro solicitado no existe en el catálogo actual.</p>
      <RouterLink class="btn btn-primary" to="/libros">Volver a libros</RouterLink>
    </div>
  </section>
</template>

<script>
import { computed } from 'vue'

export default {
  name: 'DetalleLibro',

  props: {
    id: {
      type: [String, Number],
      required: true
    }
  },

  setup(props) {
    const libros = [
      {
        id: 1,
        titulo: 'Cien años de soledad',
        autor: 'Gabriel García Márquez',
        categoria: 'Novela',
        descripcion: 'Una obra fundamental de la literatura latinoamericana.'
      },
      {
        id: 2,
        titulo: 'El principito',
        autor: 'Antoine de Saint-Exupéry',
        categoria: 'Infantil',
        descripcion: 'Una historia breve sobre la amistad, el amor y la vida.'
      },
      {
        id: 3,
        titulo: '1984',
        autor: 'George Orwell',
        categoria: 'Ciencia ficción',
        descripcion: 'Novela distópica sobre una sociedad bajo vigilancia permanente.'
      }
    ]

    const libro = computed(() =>
      libros.find((item) => item.id === Number(props.id))
    )

    return {
      libro
    }
  }
}
</script>