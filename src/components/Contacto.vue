<template>
  <section class="py-5 orange-bg" id="contacto">
    <div class="container">
      <h2 class="mb-4 text-center">Contáctanos</h2>
      <div class="row">
        <div class="col-md-6 text-start">
          <h4 class="mb-2 fw-bold">Ubicación</h4>
          <p>Luis Barros Borgoño 2630, Maipu</p>
          <h4 class="mb-2 fw-bold">Email</h4>
          <p>info@gajadacomex.cl</p>
          <h4 class="mb-2 fw-bold">Número de Contacto</h4>
          <p>+56 9 7531 9891</p>
        </div>
        <div class="col-md-6">
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
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contacto',
  props: ['formulario', 'errores', 'enviando']
};
</script>
