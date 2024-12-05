<script setup>

  import { ref } from 'vue';
  
</script>

<template>
  <div dir="rtl" class="header flex justify-between items-center bg-[#222] text-white py-4">
    <div class="mx-auto nav-container bg-[#000] border border-white rounded-xl py-4 mt-4 flex justify-between items-center w-full px-4">
      <div class="brand flex items-center">
        <router-link to="/"><img src="../assets/images/logo-black.svg" alt="Logo" class="" />
        </router-link>
      </div>
      <div class="flex gap-4">
        <router-link to="/register"
          class="btn-header px-6 py-2 text-sm rounded-full hover:bg-[#94D401] text-black transition-all" >
          حساب جديد
        </router-link>
        <router-link to="/login"
          class="btn-header px-6 py-2 text-sm rounded-full text-black bg-[#94D401] hover:bg-[#76C100] transition-all" >
          تسجيل الدخول
        </router-link>
      </div>
    </div>

  </div>
</template>

<style scoped>
  .header > div {
    width: 90%;
  }
  .nav-container {
    background-color: rgba(255, 255, 255, 0.4);
    /* backdrop-filter: blur(30px); */
    width: 90%;
  }
</style>
