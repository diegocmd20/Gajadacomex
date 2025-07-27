<template>
    <section class="py-5" id="nosotros">
        <div class="container">
            <h2 class="mb-4 text-center">Conócenos</h2>
            <div class="row">
                <div class="col-md-6 my-auto">
                    <h3 class="h4 mb-4">Trayectoria, Confianza y Soluciones Innovadoras</h3>
                    <p>En GAJADACOMEX, entendemos que el mundo del comercio internacional es complejo y dinámico. Por
                        eso,
                        hemos nacido de la visión de un fundador con 19 años de sólida experiencia en abastecimiento y
                        operaciones logísticas. Su profundo conocimiento es la base sobre la cual construimos una
                        asesoría
                        integral, diseñada para simplificar tus procesos de importación y exportación y maximizar tu
                        eficiencia.</p>
                </div>
                <div class="col-md-6"><img :src="suministro" alt="suministro" class="img-fluid" data-aos="fade-left"></div>
            </div>
            <div class="row">
                <div class="col-md-6"><img :src="logistica" alt="logistica" class="img-fluid" data-aos="fade-right"></div>
                <div class="col-md-6 my-auto">
                    <h3 class="h4 mb-4">Misión: Ejecución Experta en Tu Cadena de Suministro</h3>

                    <p>Nuestra misión es clara: proporcionar un servicio de operación logística de principio a fin,
                        desde el
                        asesoramiento estratégico hasta la ejecución final de cada proceso que compone tu cadena de
                        suministro.
                    </p>
                    <h3 class="h4 mb-4">Visión: Liderazgo y Fidelización en Logística Internacional</h3>
                    <p>Nuestra visión se basa en una
                        asesoría experta y una vasta experiencia, elementos clave que nos permiten construir relaciones
                        sólidas y duraderas, logrando la total fidelización de nuestros clientes a través de resultados
                        excepcionales.</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

import logistica from '@/assets/logistica.webp';
import suministro from '@/assets/suministro.webp';

export default {
    name: 'Nosotros',
    props: ['equipoTrabajo']
    ,
    data() {
        return {
            logistica,
            suministro
        }
    }
};
</script>