<template>
    <section class="py-5" id="servicios">
        <div class="container">
            <h2 class="mb-4 text-center">Nuestros Servicios</h2>
            <div class="row">
                <h4 class="mb-4">Eficiencia y Transparencia en Cada Paso de tu Carga</h4>
                <p>Entendemos que cada operación de comercio exterior es única y requiere un manejo preciso y continuo. En GAJADACOMEX, te ofrecemos información específica y detallada en todo momento, garantizando claridad, confianza y respuesta rápida a tus necesidades.</p>
                <div v-for="(servicio, index) in serviciosPrincipales" :key="index" class="col-md-4 mb-4">
                    <div class="card h-100" data-aos="fade-up">
                        <div class="card-body">
                            <h5 class="card-title">{{ servicio.titulo }}</h5>
                            <p class="card-text">{{ servicio.descripcion }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'ServiciosPreview',
    props: ['serviciosPrincipales']
};
</script>
