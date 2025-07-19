<template>
    <section class="py-5 bg-light" id="nosotros">
        <div class="container">
            <h2 class="mb-4 text-center">Nuestro Equipo</h2>
            <div class="row">
                <div v-for="(miembro, index) in equipoTrabajo" :key="index" class="col-md-3 mb-4">
                    <div class="card text-center" data-aos="fade-up">
                        <div class="card-body">
                            <h5 class="card-title">{{ miembro.nombre }}</h5>
                            <p class="card-text">{{ miembro.rol }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Nosotros',
    props: ['equipoTrabajo']
};
</script>