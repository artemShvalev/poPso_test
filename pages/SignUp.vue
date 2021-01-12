<template>
<div>
  <div class="container">
    <div >
      <img  class="main__logo" src="../assets/popso__logo.svg" alt="Логотип">
    </div>
    <div class="inputs__authorization">
      <v-text-field
        label="Email"
        v-model="authUser.email"
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
    <NuxtLink to="/login"><button @click="authNewUser" >Зарегистрироваться</button></NuxtLink>
  </div>
  <NuxtLink to="/login"  class="btn-sign-up">Уже есть аккаунт? Войти</NuxtLink>
</div>
</template>

<script>
export default {
  name: 'SignUp',
  data: () => {
    return {
      authUser: {
        email: 'artcom888@mail.ru',
        password: ''
      },
      rules: [
        value => !!value || 'Обязательно для заполнения',
        value => (value && value.length >= 3) || 'Минимум 6 символов',
        value => (value !== value.type) || 'Некорректный email'
      ]
    }
  },
  methods: {
    async authNewUser () {
      try {
        await this.$fire.auth.createUserWithEmailAndPassword(
          'foo@foo.foo',
          'test_test'
        )
      } catch (e) {
        alert(e)
      }
    }
  }
}
</script>

<style scoped lang=scss>
  @import 'assets/sass/index';

</style>
