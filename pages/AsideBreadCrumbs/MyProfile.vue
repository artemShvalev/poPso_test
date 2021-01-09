<template>
<div>

  <!-- Мой профиль -->
  <div class="main__container">
    <div class="profile__title">
      <h1>Мой Профиль</h1>
    </div>
    <div class="main__inputs">
      <v-text-field
        label="Имя"
        hide-details="auto"
      ></v-text-field>
      <v-text-field
        label="Фамилия"
        hide-details="auto"
      ></v-text-field>
      <v-text-field
        label="Старый пароль"
        hide-details="auto"
      ></v-text-field>
      <v-text-field
        label="Сменить Пароль"
        hide-details="auto"
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
  name: 'MyProfile'
}
</script>

<style scoped lang=scss>
  @import "assets/sass/user_profile";
  .main__container {
    background: #EFF1F9;
    position: absolute;
    top: 0;
    left: 300px;
    right: 0;
  }
</style>
