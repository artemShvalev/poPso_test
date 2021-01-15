<template>
  <div>
    <v-app-bar
      class="app__bar"
      color="#FFFFFF"
    >
      <div  :class="{openMenu}"  @click="open" >
      <img class="line line__default"  src="../assets/line.png" alt="">
      <img class="line2 line__default" src="../assets/line.png" alt="">
      </div>
    </v-app-bar>
    <div :class="{aside__none}">
    <aside :class="{step__left}" >
      <div class="profile__logo">
        <img src="../assets/popso__logo__profile.svg" alt="лого__профайла" >
      </div>
      <div class="profile__section">
        <div class="burger__menu"  @click="showBurger">
          <img src="../assets/menu__icon.svg" alt="">
          <img :class="{arrow}" class="arrow__default" src="../assets/arrow.png" alt="cтрелка">
        </div>
        <ul>
          <li ><NuxtLink to="/AsideBreadCrumbs/MyProfile"> <img  class="link__profile" src="../assets/icon__keys.svg" alt="иконка">Мой профиль</NuxtLink> </li>
          <li ><NuxtLink to="/AsideBreadCrumbs/MyTasks"><img  class="link__list" src="../assets/icon__tasks.svg" alt="иконка">Список Задач</NuxtLink></li>
          <li ><NuxtLink to="/AsideBreadCrumbs/MyStatistics"><img class="link__statistics"  src="../assets/icon__statistics.svg" alt="иконка">Статистика</NuxtLink></li>
        </ul>
      </div>
    </aside>
    </div>
    <MyProfile />
  </div>
</template>

<script>
import MyProfile from '../pages/AsideBreadCrumbs/MyProfile'

export default {
  name: 'UserProfile',
  components: { MyProfile },
  data () {
    return {
      show: false,
      step__left: false,
      arrow: false,
      openMenu: false,
      aside__none: true
    }
  },
  methods: {
    showBurger () {
      this.step__left = !this.step__left
      this.arrow = !this.arrow
    },
    open () {
      this.openMenu = !this.openMenu
      this.aside__none = !this.aside__none
    }
  }
}
</script>

<style scoped lang=scss>
  @import "assets/sass/user_profile";

</style>
