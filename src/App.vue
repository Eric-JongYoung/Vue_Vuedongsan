<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4 :class="클래스명" :style="스타일"> {{ products[0] }} 원룸</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4> {{ products[1] }} 원룸</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <div>
    <h4> {{ products[2] }} 원룸</h4>
    <p>{{ price2 }} 만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return  {
      price1 : 60,
      price2 : 70,
      스타일 : 'color : blue',
      클래스명 : 'wow',
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
