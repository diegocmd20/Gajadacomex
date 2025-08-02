<template>
  <section class="py-5 blue-bg" id="contacto">
    <div class="container">
      <h2 class="mb-4 text-center">Contáctanos</h2>
      <div class="row">
        <div class="col-md-6 text-start my-auto">
          <h4 class="mb-2"><i class="bi bi-geo-alt-fill"></i> Ubicación</h4>
          <p>Luis Barros Borgoño 2630, Maipu</p>
          <h4 class="mb-2"><i class="bi bi-envelope"></i> Email</h4>
          <p>info@gajadacomex.cl</p>
          <h4 class="mb-2"><i class="bi bi-telephone"></i> Número de Contacto</h4>
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
    <div class="container pt-5 map-section">
      <div class="row justify-content-center">
        <div class="col-12 col-md-10 col-lg-8">
          <div class="iframe-wrapper shadow rounded-4 overflow-hidden">
            <iframe class="map-iframe"
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3326.8874681980888!2d-70.78525132490186!3d-33.50430480027109!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9662c2c953f0e037%3A0x90192012a7466c4!2sLuis%20Barros%20Borgo%C3%B1o%202630%2C%20Maip%C3%BA%2C%20Regi%C3%B3n%20Metropolitana!5e0!3m2!1ses-419!2scl!4v1754152707167!5m2!1ses-419!2scl"
              allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
          </div>
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
