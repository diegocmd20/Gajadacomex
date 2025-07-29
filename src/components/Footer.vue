<template>
    <footer class="py-4 text-white text-center orange-bg">
        <div class="container d-flex flex-column align-items-center">
            <img class="logo-footer" :src="logoFooter" alt="Gajacomex-footer">
            <small>&copy; 2025 GAJADACOMEX. Todos los derechos reservados.</small>
        </div>
    </footer>
</template>

<script>
import logoFooter from '@/assets/logo-blanco.webp';

export default {
    name: 'Footer',
    data(){
        return {
            logoFooter
        }
    }
};
</script>