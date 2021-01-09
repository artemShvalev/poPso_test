<template>
<div>
  <aside>
    <div class="logo">
      <img src="../../assets/popso__logo__profile.svg" alt="лого__профайла">
    </div>
    <div class="profile__section">
      <ul>
        <li><NuxtLink to="/AsideBreadCrumbs/MyProfile"><img src="../../assets/icon__keys.svg" alt="иконка">Мой профиль</NuxtLink></li>
        <li><NuxtLink to="/AsideBreadCrumbs/MyStatistics"><img src="../../assets/icon__statistics.svg" alt="иконка">Статистика</NuxtLink></li>
      </ul>
    </div>
  </aside>
  <!-- Мои заачи -->
<div class="container">
  <div class="profile__title">
    <h1>Мои задачи</h1>
  </div>
  <div class="status">
    <ul> Задачи
      <li></li>
    </ul>
    <div class="complete">
     <span>Состояние</span>
    <span>V</span>
    <span>X</span>
    </div>
  </div>
</div>
</div>
</template>

<script>
export default {
  name: 'MyTasks'
}
</script>

<style scoped lang=scss>

</style>
