<template>
  <div>
    <aside>
      <div class="profile__logo">
        <img src="../assets/popso__logo__profile.svg" alt="лого__профайла">
      </div>
      <div class="profile__section">
        <div class="burger__menu">
          <img src="../assets/menu__icon.svg" alt="">
          <img class="arrow" src="../assets/arrow.png" alt="cтрелка">
        </div>
        <ul>
          <li><NuxtLink to="/AsideBreadCrumbs/MyProfile"> <img src="../assets/icon__keys.svg" alt="иконка">Мой профиль</NuxtLink> </li>
          <li  @click="showMyTask"><NuxtLink to="/AsideBreadCrumbs/MyTasks"><img src="../assets/icon__tasks.svg" alt="иконка">Список Задач</NuxtLink></li>
          <li><NuxtLink to="/AsideBreadCrumbs/MyStatistics"><img src="../assets/icon__statistics.svg" alt="иконка">Статистика</NuxtLink></li>
        </ul>
      </div>
    </aside>
    <MyProfile />
    <MyTasks v-show="showMyTasks"/>
  </div>
</template>

<script>
import MyProfile from './AsideBreadCrumbs/MyProfile'
import MyTasks from './AsideBreadCrumbs/MyTasks'
export default {
  name: 'UserProfile',
  components: { MyTasks, MyProfile },
  data () {
    return {
      showMyTasks: false
    }
  },
  methods: {
    showMyTask () {
      this.showMyTask = !this.showMyTask
    }
  }
}
</script>

<style scoped lang=scss>
  @import "assets/sass/user_profile";

</style>
