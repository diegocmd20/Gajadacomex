<template>
    <div>
        <div class="modal fade" id="servicioModal" tabindex="-1">
            <div class="modal-dialog">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title">{{ servicioActual.titulo }}</h5>
                        <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                    </div>
                    <div class="modal-body">
                        <p>{{ servicioActual.descripcion }}</p>
                    </div>
                </div>
            </div>
        </div>

        <div class="modal fade" id="confirmacionModal" tabindex="-1">
            <div class="modal-dialog">
                <div class="modal-content text-center">
                    <div class="modal-body">
                        <p>Formulario enviado correctamente. ¡Gracias por contactarnos!</p>
                        <button type="button" class="btn btn-success" data-bs-dismiss="modal">Cerrar</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Modales',
    props: ['servicioActual']
};
</script>