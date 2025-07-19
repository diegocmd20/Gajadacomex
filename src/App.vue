<script>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import ServiciosPreview from './components/ServiciosPreview.vue'
import Nosotros from './components/Nosotros.vue'
import ServiciosDetalle from './components/ServiciosDetalle.vue'
import Contacto from './components/Contacto.vue'
import Footer from './components/Footer.vue'
import ScrollTop from './components/ScrollTop.vue'
import Modales from './components/Modales.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Hero,
    ServiciosPreview,
    Nosotros,
    ServiciosDetalle,
    Contacto,
    Footer,
    ScrollTop,
    Modales
  },
  data() {
    return {
      scrolledNav: false,
      scrollTop: false,
      serviciosPrincipales: [
        { id: 1, titulo: 'Consultoría', descripcion: 'Soluciones a medida' },
        { id: 2, titulo: 'Soporte Técnico', descripcion: 'Asistencia 24/7' }
      ],
      serviciosCompletos: [
        { id: 1, titulo: 'Consultoría', descripcion: 'Análisis detallado para mejorar procesos.' },
        { id: 2, titulo: 'Soporte Técnico', descripcion: 'Servicio técnico especializado y rápido.' }
      ],
      equipoTrabajo: [],
      formulario: {
        nombre: '',
        email: '',
        telefono: '',
        mensaje: ''
      },
      errores: {},
      enviando: false,
      servicioActual: {},
      modalServicio: null,
      modalConfirmacion: null
    }
  },
  mounted() {
    if (window.AOS) {
      window.AOS.init({ duration: 800, once: true });
    }
    window.addEventListener('scroll', this.handleScroll);
    this.modalServicio = new window.bootstrap.Modal(document.getElementById('servicioModal'));
    this.modalConfirmacion = new window.bootstrap.Modal(document.getElementById('confirmacionModal'));
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const scrollPosition = window.scrollY;
      this.scrolledNav = scrollPosition > 50;
      this.scrollTop = scrollPosition > 300;
    },
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    },
    abrirModalServicio(servicio) {
      this.servicioActual = servicio;
      this.modalServicio.show();
    },
    validarFormulario() {
      let valido = true;
      this.errores = {
        nombre: '',
        email: '',
        telefono: '',
        mensaje: ''
      };
      if (!this.formulario.nombre.trim()) {
        this.errores.nombre = 'El nombre es obligatorio';
        valido = false;
      }
      if (!this.formulario.email.trim()) {
        this.errores.email = 'El email es obligatorio';
        valido = false;
      } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.formulario.email)) {
        this.errores.email = 'Email no válido';
        valido = false;
      }
      if (!this.formulario.telefono.trim()) {
        this.errores.telefono = 'El teléfono es obligatorio';
        valido = false;
      }
      if (!this.formulario.mensaje.trim()) {
        this.errores.mensaje = 'El mensaje es obligatorio';
        valido = false;
      }
      return valido;
    },
    enviarFormulario() {
      if (this.validarFormulario()) {
        this.enviando = true;
        setTimeout(() => {
          this.enviando = false;
          this.formulario = {
            nombre: '',
            email: '',
            telefono: '',
            mensaje: ''
          };
          this.modalConfirmacion.show();
        }, 1500);
      }
    }
  }
}
</script>

<template>
  <div id="app">
    <Navbar :scrolledNav="scrolledNav" />
    <Hero />
    <ServiciosPreview :serviciosPrincipales="serviciosPrincipales" />
    <Nosotros :equipoTrabajo="equipoTrabajo" />
    <ServiciosDetalle :serviciosCompletos="serviciosCompletos" @abrirModal="abrirModalServicio" />
    <Contacto @enviar="enviarFormulario" :formulario="formulario" :errores="errores" :enviando="enviando" />
    <Footer />
    <ScrollTop :scrollTop="scrollTop" @scroll-to-top="scrollToTop" />
    <Modales :servicioActual="servicioActual" />
  </div>
</template>

<style></style>
