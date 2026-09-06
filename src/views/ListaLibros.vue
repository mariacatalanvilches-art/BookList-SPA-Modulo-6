<template>
  <section>
    <div class="page-title">
      <div>
        <span class="eyebrow">Catálogo</span>
        <h2>Lista de libros</h2>
        <p>Agrega, consulta y elimina libros del catálogo.</p>
      </div>
      <div class="counter">
        {{ libros.length }} {{ libros.length === 1 ? 'libro' : 'libros' }}
      </div>
    </div>

    <FormularioLibro @agregar="agregarLibro" />

    <section class="catalog-section">
      <div class="section-heading">
        <div>
          <span class="eyebrow">Registros</span>
          <h2>Catálogo actual</h2>
        </div>
      </div>

      <div v-if="libros.length > 0" class="book-list">
        <Libro
          v-for="libro in libros"
          :key="libro.id"
          :id="libro.id"
          :titulo="libro.titulo"
          :autor="libro.autor"
          :categoria="libro.categoria"
          @eliminar="eliminarLibro"
        />
      </div>

      <div v-else class="empty-state">
        <span>📚</span>
        <h3>No hay libros disponibles</h3>
        <p>Utiliza el formulario superior para agregar el primer libro.</p>
      </div>
    </section>
  </section>
</template>

<script>
import Libro from '../components/Libro.vue'
import FormularioLibro from '../components/FormularioLibro.vue'

export default {
  name: 'ListaLibros',

  components: {
    Libro,
    FormularioLibro
  },

  data() {
    return {
      siguienteId: 4,
      libros: [
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
    }
  },

  methods: {
    agregarLibro(nuevoLibro) {
      this.libros.push({
        id: this.siguienteId++,
        ...nuevoLibro
      })
    },

    eliminarLibro(id) {
      this.libros = this.libros.filter((libro) => libro.id !== id)
    }
  }
}
</script>