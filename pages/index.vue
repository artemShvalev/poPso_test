<template>
<div>
<div class="container">
  <div >
    <img  class="main__logo" src="../assets/popso__logo.svg" alt="Логотип">
  </div>
  <div class="inputs__authorization">
    <v-text-field
      label="Логин"
      outlined
      :rules="rules"
      hide-details="auto"
    ></v-text-field>
    <v-text-field
      label="Пароль"
      outlined
      :rules="rules"
      hide-details="auto"
    ></v-text-field>
  </div>
  </div>
  <div class="btn">
    <NuxtLink to="/UserProfile"><button>Войти</button></NuxtLink>
  </div>
</div>
</template>
<script>
export default {
  data: () => ({
    rules: [
      value => !!value || 'Обязательно для заполнения',
      value => (value && value.length >= 3) || 'Минимум 3 символа'
    ]
  })
}
</script>

<style lang="scss">
  @import "assets/sass/index";
</style>
