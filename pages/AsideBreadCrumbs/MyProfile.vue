<template>
<div>
  <UserProfile  name="UserProfile"/>

  <!-- Мой профиль -->
  <div class="main__container">
    <div class="profile__title">
      <h1>Мой Профиль</h1>
    </div>
    <div class="main__inputs">
      <v-text-field
        label="Имя"
        hide-details="auto"
        v-model.trim="saveInfoUser.name"
        color="color"
      ></v-text-field>
      <v-text-field
        label="Фамилия"
        v-model.trim="saveInfoUser.lastName"
        hide-details="auto"
        color="#2196F3"
        :rules="rules"
      ></v-text-field>
      <v-text-field
        label="Старый пароль"
        :rules="rules"
        type="password"
        v-model.trim="saveInfoUser.oldPassword"
        hide-details="auto"
        color="#2196F3"
      ></v-text-field>
      <v-text-field
        label="Сменить Пароль"
        :rules="rules"
        v-model.trim="saveInfoUser.changePassword"
        type="password"
        hide-details="auto"
        color="#2196F3"
      ></v-text-field>
    </div>
    <div class="btn__save-ifo">
      <button  @click="saveUser">Сохранить</button>
    </div>
  </div>
</div>
</template>

<script>
import axios from 'axios'
import UserProfile from '../UserProfile.vue'
export default {
  name: 'MyProfile',
  components: { UserProfile },
  data: () => ({
    rules: [
      value => !!value || 'Обязательно для заполнения',
      value => (value && value.length >= 6) || 'Минимум 6 символов'
    ],
    saveInfoUser: {
      name: '',
      lastName: '',
      oldPassword: '',
      changePassword: ''
    },
    myProfileShow: false
  }),
  methods: {
    saveUser () {
      axios.post('https://popso-d8780-default-rtdb.firebaseio.com/saveInfoUser.json', this.saveInfoUser)
        .then(result => console.log(result))
        .catch(e => console.log(e))
      this.saveInfoUser = ''
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
  .v-alert__content{
    font-family: Montserrat,sans-serif;
    padding-left: 45px;
  }
</style>
