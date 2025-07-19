<template>
    <section class="py-5" id="contacto">
    <div class="container">
      <h2 class="mb-4 text-center">Contáctanos</h2>
      <form @submit.prevent="$emit('enviar')" data-aos="fade-up">
        <div class="mb-3">
          <input type="text" class="form-control" placeholder="Nombre" v-model="formulario.nombre">
          <small class="text-danger">{{ errores.nombre }}</small>
        </div>
        <div class="mb-3">
          <input type="email" class="form-control" placeholder="Correo electrónico" v-model="formulario.email">
          <small class="text-danger">{{ errores.email }}</small>
        </div>
        <div class="mb-3">
          <input type="text" class="form-control" placeholder="Teléfono" v-model="formulario.telefono">
          <small class="text-danger">{{ errores.telefono }}</small>
        </div>
        <div class="mb-3">
          <textarea class="form-control" rows="4" placeholder="Mensaje" v-model="formulario.mensaje"></textarea>
          <small class="text-danger">{{ errores.mensaje }}</small>
        </div>
        <button type="submit" class="btn btn-primary" :disabled="enviando">Enviar</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
    name: 'Contacto',
    props: ['formulario', 'errores', 'enviando']
};
</script>
