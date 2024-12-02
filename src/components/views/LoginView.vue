<script setup>
import { reactive } from "vue";

const form = reactive({
  username: "",
  password: "",
});

</script>

<template>
  <div class="mt-12 mb-12">
    <div class="container mx-auto flex flex-wrap lg:flex-nowrap justify-between items-center">
      <!-- Left Section -->
      <div class="hidden sm:hidden lg:block w-full lg:w-1/2">
        <img src="../../assets/images/login-img.png" alt="Login" class="w-full">
      </div>

      <!-- Right Section -->
      <div class="w-full lg:w-1/2 px-6 lg:px-12 text-right">
        <h1 class="text-4xl font-bold text-gray-800 mb-4 text-center relative">
           <span> مرحباً بعودتك</span>
           <img src="../../assets/icons/waving.png" class="absolute bottom-0 sm:left-52 lg:left-20 md:left-56" width="40" alt="">
        </h1>
        <p dir="rtl" class="text-lg text-gray-600 mb-8 text-center">
            ادخل بياناتك لمتابعة اخر تطورات وظائفك واجد الفرص المميزة.
        </p>
      
        <form @submit.prevent="" class="space-y-6 mx-auto max-w-md">
          <div class="flex flex-col text-right">
            <label for="username" class="mb-1 text-gray-600"> اسم المستخدم أو البريد الإلكتروني</label>
            <input
              id="username"
              type="text"
              v-model="form.username"
              class="border-b border-gray-300 focus:outline-none focus:border-gray-500 py-2">
          </div>

          <div class="flex flex-col text-right relative">
            <label for="password" class="mb-1 text-gray-600">كلمة المرور</label>
            <i class="pi pi-eye text-left absolute bottom-4"></i>
            <input
              id="password"
              type="password"
              v-model="form.password"
              class="border-b border-gray-300 focus:outline-none focus:border-gray-500 py-2">
          </div>
          <!-- Remember Me -->
          <div class="flex justify-between items-center space-x-2 space-x-reverse text-right" dir="rtl">
              <div>
                <input
              id="agreeToTerms"
              type="checkbox"
              v-model="form.agreeToTerms"
              class="h-4 w-4 border-gray-300 rounded"/> 
              <span > تذكرني؟</span>
              </div>
              <span class="forget-password">نسيت كلمة المرور؟</span>
          </div>

          <button
            type="submit"
            class="w-full text-white py-3 rounded-full"
          >
            تسجيل الدخول
          </button>
        </form>

        <p class="mt-4 text-center text-gray-600">
          ليس لديك حساب؟ 
          <router-link to="/register" class="link underline">إنشاء حساب جديد</router-link>
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
label {
    color: #D0D0DC;
}
button {
    background-color: #222222;
}
.link, .forget-password {
    color: #94D401;
}

</style>
