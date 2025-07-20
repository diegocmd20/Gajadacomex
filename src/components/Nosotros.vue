<template>
    <section class="py-5 bg-light" id="nosotros">
        <div class="container">
            <h2 class="mb-4 text-center">Quiénes somos</h2>
            <div class="row">
                <h3 class="h4 mb-4">Nuestra Historia</h3>
                <p>Su Fundador, con 19 años de experiencia en departamentos de abastecimiento y operación en logística,
                    crea GAJADACOMEX con el sueño de traspasar sus conocimientos en beneficio de sus clientes a través
                    de
                    una asesoría integral en logística y comercio internacional.</p>

                <p>Tranquilidad, respaldo, seguridad y sustentabilidad en el proceso.</p>

                <p>Al desarrollar funciones relacionadas al área de operaciones, complementando el control y
                    trazabilidad
                    de los procesos, hoy le permiten proyectar con rapidez nuevas ideas que aporten a la mejora
                    continua,
                    con el fin de satisfacer las necesidades particulares de cada cliente a través de la reducción de
                    costos, tiempos de entrega, seguridad de los productos y apertura de negocios.</p>

                <h3 class="h4 mb-4">Misión</h3>
                <p>Proporcionar un servicio de operación logística desde el asesoramiento hasta la ejecución final de
                    los procesos que involucran la cadena de suministro. Todo esto utilizando las distintas
                    herramientas, áreas y tecnologías especialmente creadas para su desarrollo.</p>
                <h3 class="h4 mb-4">Visión</h3>
                <p>Ser una empresa líder y de confianza que impulsa el desarrollo de negocios de personas y
                    organizaciones a través del proceso logístico, basado en la asesoría y experiencia, logrando así la
                    fidelización de sus clientes.</p>
                <!-- <div v-for="(miembro, index) in equipoTrabajo" :key="index" class="col-md-3 mb-4">
                    <div class="card text-center" data-aos="fade-up">
                        <div class="card-body">
                            <h5 class="card-title">{{ miembro.nombre }}</h5>
                            <p class="card-text">{{ miembro.rol }}</p>
                        </div>
                    </div>
                </div> -->
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