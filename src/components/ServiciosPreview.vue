<template>
    <section class="py-5" id="servicios">
        <div class="container">
            <h2 class="mb-4 text-center">Servicios Principales</h2>
            <div class="row">
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
