<template>
  <section class="form-section">
    <div class="section-heading">
      <div>
        <span class="eyebrow">Nuevo registro</span>
        <h2>Agregar un libro</h2>
      </div>
      <span class="live-indicator">● Datos en tiempo real</span>
    </div>

    <form @submit.prevent="agregarLibro">
      <div class="form-grid">
        <div class="form-group">
          <label for="titulo">Título</label>
          <input
            id="titulo"
            v-model="formulario.titulo"
            type="text"
            placeholder="Ej.: Cien años de soledad"
            required
          />
        </div>

        <div class="form-group">
          <label for="autor">Autor</label>
          <input
            id="autor"
            v-model="formulario.autor"
            type="text"
            placeholder="Ej.: Gabriel García Márquez"
            required
          />
        </div>

        <div class="form-group">
          <label for="categoria">Categoría</label>
          <select id="categoria" v-model="formulario.categoria" required>
            <option disabled value="">Selecciona una categoría</option>
            <option>Novela</option>
            <option>Fantasía</option>
            <option>Ciencia ficción</option>
            <option>Historia</option>
            <option>Romance</option>
            <option>Infantil</option>
            <option>Otro</option>
          </select>
        </div>

        <div class="form-group full-width">
          <label for="descripcion">Descripción</label>
          <textarea
            id="descripcion"
            v-model="formulario.descripcion"
            rows="3"
            placeholder="Escribe una breve descripción del libro..."
          ></textarea>
        </div>
      </div>

      <div class="preview-box" v-show="hayDatos">
        <h3>Vista previa en tiempo real</h3>
        <p><strong>Título:</strong> {{ formulario.titulo || 'Sin ingresar' }}</p>
        <p><strong>Autor:</strong> {{ formulario.autor || 'Sin ingresar' }}</p>
        <p><strong>Categoría:</strong> {{ formulario.categoria || 'Sin seleccionar' }}</p>
        <p><strong>Descripción:</strong> {{ formulario.descripcion || 'Sin ingresar' }}</p>
      </div>

      <button class="btn btn-primary" type="submit" @click.once="registrarPrimerClick">
        + Agregar libro
      </button>
    </form>
  </section>
</template>

<script>
export default {
  name: 'FormularioLibro',

  emits: ['agregar'],

  data() {
    return {
      formulario: {
        titulo: '',
        autor: '',
        categoria: '',
        descripcion: ''
      }
    }
  },

  computed: {
    hayDatos() {
      return Object.values(this.formulario).some((valor) => valor.trim() !== '')
    }
  },

  methods: {
    agregarLibro() {
      if (!this.formulario.titulo.trim() || !this.formulario.autor.trim() || !this.formulario.categoria) {
        return
      }

      this.$emit('agregar', {
        titulo: this.formulario.titulo.trim(),
        autor: this.formulario.autor.trim(),
        categoria: this.formulario.categoria,
        descripcion: this.formulario.descripcion.trim()
      })

      this.formulario = {
        titulo: '',
        autor: '',
        categoria: '',
        descripcion: ''
      }
    },

    registrarPrimerClick() {
      // Se ejecuta una sola vez gracias al modificador @click.once.
    }
  }
}
</script>