<template>
<div>
  <aside>
    <div class="profile__logo">
      <img src="../../assets/popso__logo__profile.svg" alt="лого__профайла">
    </div>
    <div class="profile__section">
      <div class="burger__menu">
        <img src="../../assets/menu__icon.svg" alt="">
        <img class="arrow" src="../../assets/arrow.png" alt="cтрелка">
      </div>
      <ul>
        <li><NuxtLink to="/AsideBreadCrumbs/MyProfile"> <img src="../../assets/icon__keys.svg" alt="иконка">Мой профиль</NuxtLink> </li>
        <li><NuxtLink to="/AsideBreadCrumbs/MyTasks"><img src="../../assets/icon__tasks.svg" alt="иконка">Список Задач</NuxtLink></li>
        <li><NuxtLink to="/AsideBreadCrumbs/MyStatistics"><img src="../../assets/icon__statistics.svg" alt="иконка">Статистика</NuxtLink></li>
      </ul>
    </div>
  </aside>

  <!-- Мои заачи -->
  <div class="container">
    <div class="profile__title">
      <h1>Список задач</h1>
    </div>
    <div class="tasks__box">
      <div class="status">
        <div class="title__task">
          <h3>Задача</h3>
        </div>
        <div class="task__container">
          <ul>
            <li>123123123</li>
            <li>12312312312</li>
          </ul>
        </div>
        <div class="complete">
          <h3>Статус</h3>
          <v-checkbox
            label="Выполнено"
            color="#299a0b"
            value="success"
            hide-details
            :multiple = true
          ></v-checkbox>
          <v-checkbox
            label="Выполнено"
            color="#299a0b"
            value="success"
            hide-details
            :multiple = true
          ></v-checkbox>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MyTasks',
  data: () => {
    return {
    }
  }
}
</script>

<style scoped lang=scss>
  @import "assets/sass/user_profile";

  .container{
    width:100vw;
    height: 100vh;
    background: #EFF1F9;
    position: absolute;
    left: 300px;
    top: 0;
  }
  .profile__title{
    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 32px;
    color: #303136;
    margin-top: 40px;
    margin-left: 48px;
  }

  .tasks__box{
    position: absolute;
    width: 920px;
    height: 359px;
    left: 46px;
    top: 120px;
    background: #FFFFFF;
    border-radius: 10px;
  }
  .title__task{
    position: absolute;
    width: 185px;
    height: 16px;
    left: 40px;
    top: 32px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 16px;
    color: #BABABA;
  }
  .status{
  }
  .complete{
    position: absolute;
    width: 48px;
    height: 16px;
    right: 113px;
    top: 32px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 16px;
    text-align: right;
    color: #BABABA;
  }
  .task__container{
    position: absolute;
    left: 40px;
    top: 65px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 16px;
    color: #303136;
  }

</style>
