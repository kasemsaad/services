<script setup>
import RegisterView from './components/views/RegisterView.vue';
import LoginView from './components/views/LoginView.vue';
import Home from './components/Home.vue';
import Footer from './components/Footer.vue';
import { RouterView } from 'vue-router';
</script>

<template>
    <!-- <RegisterView />
    <LoginView /> -->
    
    <router-view />
    <!-- <Home /> -->
    <Footer />
    
</template>

<style scoped>

</style>
