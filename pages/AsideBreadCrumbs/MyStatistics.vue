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

  <!-- Граффик-->

  <div class="container">
    <div class="statistic__title">
      <h2>Моя статистика</h2>
    </div>
    <div class="graphic__container">
      <v-sparkline
        color="#2196F3"
        :value="value.value1"
        :fill="fill"
        smooth
        auto-draw
        show-labels
        :padding="padding"
        :line-width="width"
        :stroke-linecap="lineCap"
        :type="type"
        :auto-line-width="autoLineWidth"
      ></v-sparkline>
      <slot></slot>
      <v-sparkline
        smooth
        color="#EEBD72"
        :value="value.value2"
        show-labels
        :fill="fill"
        auto-draw
        :padding="padding"
        :line-width="width"
        :stroke-linecap="lineCap"
        :type="type"
        :auto-line-width="autoLineWidth"
      ></v-sparkline>
      <span class="statistic__title"  v-if="this.value.value1 && this.value.value2 !== this.value.value1 && this.value.value2 ">
        {{ message }}
      </span>
    </div>
    <div class="btn_graph">
      <button class="btn__values" @click="randomNumbers">Случайные данные</button>
      <button class="btn__values-in" @click="addDate(1, 10)">Добавить Данные</button>
      <button class="btn__values-del"  @click="delDate">Удалить Данные</button>
      <button class="btn__values-incr"  @click="addDate(1, 10)">Увеличить кол-во данных</button>
      <button class="btn__values-min"  @click="delDate">Уменьшить кол-во данных</button>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MyStatistics',
  data: () => ({
    message: 'Больше графиков нет :)',
    width: 0.9,
    radius: 10,
    padding: 2,
    lineCap: 'round',
    value: {
      value1: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0], // значения можно динамически менять
      value2: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0] // значения можно динамически менять
    },
    gradientDirection: 'top',
    fill: false,
    type: 'trend',
    autoLineWidth: true
  }),
  computed: {},
  methods: {
    randomNumbers () {
      this.value.value1.sort()
      this.value.value1.splice(0, (1 / (Math.random())))
      this.value.value2.sort()
      this.value.value2.splice(0, (1 / (Math.random())))
      // if (this.value.value1 && this.value.value2 === null) {
      //   this.message
      // }
    },
    addDate (min, max) {
      this.value.value1.push(Math.round(Math.random() * (min + max)))
      this.value.value2.push(Math.round(Math.random() * (min + max)))
    },
    delDate () {
      this.value.value1.splice(0, 2)
      this.value.value2.splice(0, 2)
    }
  }
}
</script>

<style scoped lang=scss>
  @import 'assets/sass/user_profile';

  .container{
    width:100vw;
    height: 100vh;
    background: #EFF1F9;
    position: absolute;
    left: 300px;
    top: 0;
  }
  .statistic__title{
    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 32px;
    color: #303136;
    margin-top: 40px;
    margin-left: 48px;
  }
  .graphic__container{
    position: absolute;
    width: 920px;
    height: 660px;
    left: 46px;
    top: 120px;
    background: #FFFFFF;
    border-radius: 10px;
  }
  .btn_graph{
    position: absolute;
    left: 60px;
    top: 720px;
  }
  .btn__values{
    width: 145px;
    height: 32px;
    margin-right: 10px;
    border: 1px solid #CBCBCB;
    outline:none;
    box-sizing: border-box;
    border-radius: 10px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    text-align: center;
  }
  .btn__values:hover{
    border: 1px solid #BD0D22;
    box-sizing: border-box;
    border-radius: 10px;
    color:#BD0D22 ;
  }

  .btn__values-in{
    width: 145px;
    height: 32px;
    margin-right: 10px;
    border: 1px solid #CBCBCB;
    outline:none;
    box-sizing: border-box;
    border-radius: 10px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    text-align: center;
  }
  .btn__values-in:hover{
    border: 1px solid #BD0D22;
    box-sizing: border-box;
    border-radius: 10px;
    color:#BD0D22 ;
  }
  .btn__values-del{
    width: 145px;
    height: 32px;
    margin-right: 10px;
    border: 1px solid #CBCBCB;
    outline:none;
    box-sizing: border-box;
    border-radius: 10px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    text-align: center;
  }
  .btn__values-del:hover{
    border: 1px solid #BD0D22;
    box-sizing: border-box;
    border-radius: 10px;
    color:#BD0D22 ;
  }
  .btn__values-incr{
      width: 200px;
      height: 32px;
      margin-right: 10px;
      border: 1px solid #CBCBCB;
      outline:none;
      box-sizing: border-box;
      border-radius: 10px;

      font-family: Montserrat,sans-serif;
      font-style: normal;
      font-weight: 500;
      font-size: 12px;
      line-height: 16px;
      text-align: center;
  }
  .btn__values-incr:hover{
    border: 1px solid #BD0D22;
    box-sizing: border-box;
    border-radius: 10px;
    color:#BD0D22 ;
  }
  .btn__values-min{
    width: 185px;
    height: 32px;
    margin-right: 10px;
    border: 1px solid #CBCBCB;
    outline:none;
    box-sizing: border-box;
    border-radius: 10px;

    font-family: Montserrat,sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    text-align: center;
  }
  .btn__values-min:hover{
    border: 1px solid #BD0D22;
    box-sizing: border-box;
    border-radius: 10px;
    color:#BD0D22 ;
  }
</style>
