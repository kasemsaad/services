<script setup>
  import { reactive, ref } from "vue";

const form = reactive({
  name: "",
  username: "",
  email: "",
  phoneCode: "+20",
  phoneNumber: "",
  password: "",
  confirmPassword: "",
  agreeToTerms: false,
});

const isFreelancer = ref(true);

const selectUserType = (type) => {
  isFreelancer.value = type === "freelancer";
};

</script>

<template>
  <div class="registeration mb-12">
    <div class="container">
      <div class="left-section sm:hidden lg:block md:block">
        <img src="../../assets/images/register-img.png" alt="">
      </div>
      <div class="right-section">
      <h1>كن جزءًا من عائلة جوولانسر</h1>
      <p>انضم إلى عائلة جوولانسر واكتشف العديد من الفرص المميزة لعملك وشركتك.</p>
      <div class="user-type-buttons">
        <button :class="{ active: isFreelancer }" @click="selectUserType('freelancer')">مستقل</button>
        <button :class="{ active: !isFreelancer }" @click="selectUserType('client')">صاحب عمل</button>
      </div>
        <!-- Registration Form -->
        <form @submit.prevent="" class="space-y-4 pt-4 max-w-md text-center">
        <div class="flex flex-col text-right  ">
          <label for="name" class="mb-1">الاسم</label>
          <input
            id="name"
            type="text"
            v-model="form.name"
            class="border outline-none border-b-1 border-t-0 border-l-0 border-r-0"
          />
        </div>
        <div class="flex flex-col text-right">
          <label for="username" class="mb-1">اسم المستخدم</label>
          <input
            id="username"
            type="text"
            v-model="form.username"
            class="border outline-none border-b-1 border-t-0 border-l-0 border-r-0"
          />
        </div>
        <div class="flex flex-col text-right">
          <label for="email" class="mb-1">البريد الإلكتروني</label>
          <input
            id="email"
            type="email"
            v-model="form.email"
            class="border outline-none border-b-1 border-t-0 border-l-0 border-r-0"
          />
        </div>
        <div class="flex flex-col text-right">
          <label for="phone" class="mb-1">رقم الهاتف</label>
          <div class="flex gap-2">
            <select name="" id="" class="border outline-none border-b-1 border-t-0 border-l-0 border-r-0">
              <option
              id="phoneCode"
              type="text"   
            >+20</option>
            </select>
            <input
              id="phoneNumber"
              type="text"
              v-model="form.phoneNumber"
              class="border outline-none border-b-1 border-t-0 border-l-0 border-r-0 flex-1"
            />
          </div>
        </div>
        <div class="password">
          <div class="flex flex-col text-right">
          <label for="password" class="mb-1">كلمة المرور</label>
          <input
            id="password"
            type="password"
            v-model="form.password"
            class="border outline-none border-b-1 border-t-0 border-l-0 border-r-0"
          />
        </div>
        <div class="flex flex-col text-right">
          <label for="confirmPassword" class="mb-1">تأكيد كلمة المرور</label>
          <input
            id="confirmPassword"
            type="password"
            v-model="form.confirmPassword"
            class="border outline-none border-b-1 border-t-0 border-l-0 border-r-0"
          />
        </div>
        </div>
        <div class="flex items-center space-x-2 space-x-reverse text-right">
            <input
              id="agreeToTerms"
              type="checkbox"
              v-model="form.agreeToTerms"
              class="h-4 w-4 border-gray-300 rounded"
            />
            <label for="agreeToTerms" class="text-sm text-black">
              أقبل كافة <a href="#" class="text-black underline">الشروط والأحكام</a> <a href="#" class="text-black underline">وسياسة الخصوصية.</a>
            </label>
          </div>
        <div class="pt-1">
          <button type="submit" class="submit-button">إنشاء حساب</button>
        </div>
        </form>
      <p class="login-link">لديك حساب بالفعل؟ <router-link to="/login" class="underline link">تسجيل الدخول</router-link></p>
    </div>
    </div>
  </div>
</template>

<style scoped>
  .registeration {
    margin-top: 50px;
  }
  .container {
    width: 95% !important;
    display: flex;
    justify-content: space-between;
    margin: auto;
  }

  .container .left-section {
    width: 500px;
  }

.right-section {
  flex: 1.5;
  padding: 1rem;
  direction: rtl;
}

h1 {
  color: #333;
  font-weight: bold;
  font-size: 36px;
}
.right-section p {
  font-size: 16px;
}
.link {
  color: #94D401;
}

.right-section h1, .right-section p {
  text-align: center;
}
.user-type-buttons {
  display: flex;
  justify-content: space-around;
  margin: 12px 0;
  background-color: #222222;
  border-radius: 100px;
  padding: 4px 0px;
  font-size: 18px;
  max-width: 420px;
}

.user-type-buttons button {
  padding: 7px 73px;
  /* width: 249px;
  height: 50px; */
  border: none;
  cursor: pointer;
  border-radius: 100px;
  color: white;
  outline: none;
}

.user-type-buttons .active {
  background-color: #94D401;
  color: white;
}

input {
  border-bottom: 1px solid #D0D0C8;
}
.phone-group {
  display: flex;
}

.phone-group input {
  margin-right: 0.5rem;
}
label:not(:last-child) {
  color: #D0D0C8;
}
.submit-button {
  border: none;
  cursor: pointer;
  background-color: #222222;
  color: white;
  border-radius: 100px;
  padding: 6px 0px;
  font-size: 18px;
  width: 448px;
  display: block;
  margin-top: 20px;
  
}
.password {
  display: flex;
  justify-content: space-between;
}
.login-link {
  text-align: center;
  margin-top: 12px;
}
.login-link a {
  color: #94D401;
  text-decoration: underline;
}
</style>
