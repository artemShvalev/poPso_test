<template>
<div>
  <aside>
    <div class="logo">
      <img src="../../assets/popso__logo__profile.svg" alt="лого__профайла">
    </div>
    <div class="profile__section">
      <ul>
        <li><NuxtLink to="/AsideBreadCrumbs/MyProfile"><img src="../../assets/icon__keys.svg" alt="иконка">Мой профиль</NuxtLink></li>
        <li><NuxtLink to="/AsideBreadCrumbs/MyProfile"><img src="../../assets/icon__keys.svg" alt="иконка">Мой профиль</NuxtLink></li>
      </ul>
    </div>
  </aside>

  <!-- Граффик-->

  <div class="container">
    <div class="statistic__title">
      <h2>Моя статистика</h2>
    </div>
    <div class="graphic__container">
      <v-sparkline
        color="#2196F3"
        :value="value"
        :fill="fill"
        auto-draw
        :padding="padding"
        :line-width="width"
        :stroke-linecap="lineCap"
        :type="type"
        :auto-line-width="autoLineWidth"
      ></v-sparkline>
      <v-sparkline
        color="#EEBD72"
        :value="value2"
        :fill="fill"
        auto-draw
        :padding="padding"
        :line-width="width"
        :stroke-linecap="lineCap"
        :type="type"
        :auto-line-width="autoLineWidth"
      ></v-sparkline>
    </div>
    <div class="btn_graph">
      <button>Случайные данные</button>
      <button>Добавить Данные</button>
      <button>Удалить Данные</button>
      <button>Увеличить кол-во данных</button>
      <button>Уменьшить кол-во данных</button>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MyStatistics',
  data: () => ({
    width: 1,
    radius: 10,
    padding: 2,
    lineCap: 'round',
    value: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0], // значения можно динамически менять
    value2: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0], // значения можно динамически менять
    gradientDirection: 'top',
    fill: false,
    type: 'trend',
    autoLineWidth: false
  })
}
</script>

<style scoped lang=scss>

</style>
