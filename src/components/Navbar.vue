<template>
    <nav class="navbar navbar-expand-lg navbar-light navbar-custom fixed-top" :class="{ 'shadow-sm': scrolledNav }">
        <div class="container">
            <a class="navbar-brand" href="#" ><img :src="logo" alt="logo" width="50"></a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item"><a class="nav-link" href="#">Inicio</a></li>
                    <li class="nav-item"><a class="nav-link" href="#nosotros">Quiénes Somos</a></li>
                    <li class="nav-item"><a class="nav-link" href="#servicios">Servicios</a></li>
                    <li class="nav-item"><a class="nav-link" href="#contacto">Contacto</a></li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>

import logo from '@/assets/logo-horizontal.png';

export default {
    name: 'Navbar',
    props: {
        scrolledNav: {
            type: Boolean,
            default: false
        }
    },
    data() {
        return {
            logo
        }
    }
};
</script>