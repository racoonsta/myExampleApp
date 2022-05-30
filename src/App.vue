<template>
  <div class="container">
  <img alt="Vue logo" class="img__logo" src="logo.png">
  <h1>Страница выполнена с использованием библиотеки Vue JS 3</h1>
  <h2>Привожу примеры выполненных работ</h2>
    <div class="examples">
      <CardComponent v-for="card in cards"
      :key="card.id"
      :cardRecord = "card"
      />
    </div>
  </div>
</template>

<script>
import CardComponent from '@/components/CardComponent.vue'

export default {
  name: 'App',
  data () {
    return {
      cards: [
        {
          id: 1,
          sImage: './wordpress.png',
          sWork: 'Wordpress',
          sTitle1: 'Статика',
          sTitle2: '',
          sTitle3: '',
          sGithubLink: ''
        },
        {
          id: 2,
          sImage: './Uber.png',
          sWork: 'Uber',
          sTitle1: 'Статика',
          sTitle2: 'Адаптированно',
          sTitle3: '',
          sGithubLink: ''
        },
        {
          id: 3,
          sImage: './pulsmeter.png',
          sWork: 'Пульсометры',
          sTitle1: 'Адаптированно',
          sTitle2: 'JavaScript',
          sTitle3: 'Webpack',
          sGithubLink: 'https://github.com/racoonsta/pulse-on-webpack.git'
        }
      ]
    }
  },
  components: {
    CardComponent
  }
}
</script>

<style>
#app {
  display: block;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 16px;
  min-width: 320px;
}
body {
  margin: 0 0;
}
.container {
  display: inherit;
  max-width: 950px;
  margin: 0 auto;
}
.img__logo {
  width: 140px;
  height: 140px;
}
h1 {
  margin: 0 0;
  font-size: 30px;
  font-weight: 500;
  line-height: 36px;
  color: #282e3b
}
h2 {
  margin: 10px 0;
  font-size: 26px;
  font-weight: 500;
  line-height: 32px;
  color: #282e3b
}
.examples {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-wrap: wrap;
  position: relative;
}
</style>
