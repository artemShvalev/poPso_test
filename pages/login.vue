<template>
<div>
<div class="container">
  <div >
    <img  class="main__logo" src="../assets/popso__logo.svg" alt="Логотип">
  </div>
  <div class="inputs__authorization">
    <v-text-field
      label="Email"
      v-model="authUser.login"
      type="email"
      outlined
      :rules="rules"
      hide-details="auto"
    ></v-text-field>
    <v-text-field
      label="Пароль"
      v-model="authUser.password"
      type="password"
      outlined
      :rules="rules"
      hide-details="auto"
    ></v-text-field>
  </div>
  </div>
  <div class="btn">
    <NuxtLink to="/AsideBreadCrumbs/MyProfile"><button>Войти</button></NuxtLink>
  </div>
  <div >
    <NuxtLink to="/SignUp"  class="btn-sign-up">Зарегистрироваться?</NuxtLink>
  </div>
</div>
</template>

<script>

export default {
  data: () => ({
    rules: [
      value => !!value || 'Обязательно для заполнения',
      value => (value && value.length >= 3) || 'Минимум 6 символов'
    ],
    authUser: {
      email: '',
      password: ''
    }
  }),
  methods: {
  }
}
</script>

<style lang="scss">
  @import "assets/sass/index";
</style>
