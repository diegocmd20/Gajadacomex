<template>
    <section class="py-5">
        <div class="container">
            <h2 class="mb-4 text-center">Todos los Servicios</h2>
            <div class="row">
                <div v-for="(servicio, index) in serviciosCompletos" :key="index" class="col-md-4 mb-4">
                    <div class="card h-100" data-aos="fade-up">
                        <div class="card-body">
                            <h5 class="card-title">{{ servicio.titulo }}</h5>
                            <p class="card-text">{{ servicio.descripcion }}</p>
                            <button class="btn btn-primary" @click="$emit('abrirModal', servicio)">Ver más</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'ServiciosDetalle',
    props: ['serviciosCompletos']
};
</script>