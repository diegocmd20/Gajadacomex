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
        { titulo: 'Asesorías', descripcion: 'Asesórate con nosotros y toma la mejor decisión de cómo manejar el tránsito de tus productos y cargas. Lo más importante es acompañarte para que logres una compra sin contratiempos y de igual forma que te permita generar importantes negocios.' },
        { titulo: 'Evaluación de costos cargas nacionales e internacionales', descripcion: 'Valorización de cargas entre 24 a 48 hrs., bajo información previa proporcionada por su proveedor, con la finalidad de estimar sus costos reales y tiempos de tránsito según necesidad y urgencia.' },
        { titulo: 'Importación y Exportación', descripcion: 'Ejecución de importación y exportación de cargas según valorización previa, validando con el cliente las condiciones de compra y venta, bajo las cuales éstas serán tramitadas. Contamos con embarcadores con excelentes tarifas para el transporte de carga vía courrier, aérea, marítimo (LCL/FCL) y terrestre.' },
        { titulo: 'Revisión de cargas en planta o dependencias del cliente', descripcion: 'Revisión física, validando estado de la carga y posibles daños, toma de fotografías, activación de seguro de ser necesario.' },
        { titulo: 'Tramitación aduanera', descripcion: 'Internación según exigencias de aduana, para su posterior liberación y entrega en el lugar establecido.' },
        { titulo: 'Transportes Internos', descripcion: 'Servicio de transporte interno (post tramitación aduanera) desde puerto y/o aeropuerto a su empresa y viceversa' }
      ],
      serviciosCompletos: [],
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
    <Nosotros :equipoTrabajo="equipoTrabajo" />
    <ServiciosPreview :serviciosPrincipales="serviciosPrincipales" />
    <!-- <ServiciosDetalle :serviciosCompletos="serviciosCompletos" @abrirModal="abrirModalServicio" /> -->
    <Contacto @enviar="enviarFormulario" :formulario="formulario" :errores="errores" :enviando="enviando" />
    <Footer />
    <ScrollTop :scrollTop="scrollTop" @scroll-to-top="scrollToTop" />
    <Modales :servicioActual="servicioActual" />
  </div>
</template>

<style></style>
