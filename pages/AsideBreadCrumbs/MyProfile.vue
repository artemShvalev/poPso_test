<template>
<div>
  <aside v-show="myProfile" >
    <div class="profile__logo">
      <img src="../../assets/popso__logo__profile.svg" alt="лого__профайла">
    </div>
    <div class="profile__section">
      <div class="burger__menu">
        <img src="../../assets/menu__icon.svg" alt="">
        <img class="arrow" src="../../assets/arrow.png" alt="cтрелка">
      </div>
      <ul>
        <li  @click="myProfil"><NuxtLink to="/AsideBreadCrumbs/MyProfile"> <img src="../../assets/icon__keys.svg" alt="иконка">Мой профиль</NuxtLink> </li>
        <li><NuxtLink to="/AsideBreadCrumbs/MyTasks"><img src="../../assets/icon__tasks.svg" alt="иконка">Список Задач</NuxtLink></li>
        <li><NuxtLink to="/AsideBreadCrumbs/MyStatistics"><img src="../../assets/icon__statistics.svg" alt="иконка">Статистика</NuxtLink></li>
      </ul>
    </div>
  </aside>

  <!-- Мой профиль -->
  <div class="main__container">
    <div class="profile__title">
      <h1>Мой Профиль</h1>
    </div>
    <div class="main__inputs">
      <v-text-field
        label="Имя"
        hide-details="auto"
        color="color"
      ></v-text-field>
      <v-text-field
        label="Фамилия"
        hide-details="auto"
        color="#2196F3"
        :rules="rules"
      ></v-text-field>
      <v-text-field
        label="Старый пароль"
        hide-details="auto"
        color="#2196F3"
      ></v-text-field>
      <v-text-field
        label="Сменить Пароль"
        hide-details="auto"
        color="#2196F3"
      ></v-text-field>
    </div>
    <div class="btn__save-ifo">
      <button>Сохранить</button>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MyProfile',
  data: () => ({
    rules: [
      value => !!value || 'Обязательно для заполнения',
      value => (value && value.length >= 3) || 'Минимум 3 символа'
    ],
    color: [
      value => !!value || '#F44336',
      value => (value && value.length >= 3) || 'Минимум 3 символа', '#F44336'
    ],
    myProfile: false
  }),
  methods: {
    myProfil () {
      this.myProfile = this.myProfil
    }
  }
}
</script>

<style scoped lang=scss>
  @import "assets/sass/user_profile";
  @import 'assets/sass/font';
  .main__container {
    height: 100vh;
    background: #EFF1F9;
    position: absolute;
    top: 0;
    left: 300px;
    right: 0;
  }
  .profile__title{
    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 32px;
    color: #303136;
    margin-top: 40px;
    margin-left: 50px;
  }
  .main__inputs{
    max-width: 920px;
    height: 240px;
    background: #FFFFFF;
    border-radius: 10px;
    margin-top: 40px;
    margin-left: 50px;
  }
  .v-input {
    align-items: flex-start;
    display: flex;
    flex: 1 1 auto;
    font-size: 16px;
    letter-spacing: normal;
    max-width: 360px;
    text-align: left;
    margin-left: 40px;
  }
  input{
    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 16px;
    color: #6F849C;
  }
  .v-label{
    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 16px;
    color: #6F849C;
  }
  .v-text-field__slot{
    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 16px;
    color: #6F849C;
  }
  .v-messages__message{
    color:red;
    font-family:Montserrat, sans-serif ;
  }
  .v-messages__wrapper{
    color:red;
    font-family:Montserrat, sans-serif ;
  }

  .btn__save-ifo{
    background: #D6073D;
    border-radius: 10px;
    width: 202px;
    height: 44px;

    position: absolute;
    left: 650px;
    top: 235px;
  }
  button{
    text-align: center;
    width: 202px;
    height: 44px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #FFFFFF;

  }
</style>
