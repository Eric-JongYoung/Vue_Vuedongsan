<template>
  <div class="menu">
    <!-- <a v-for="작명 in 3" :key="작명">Home</a> -->
    <a v-for="i in 메뉴들" :key="i">{{ i }}</a>
    <!-- <a v-for="(a,i) in 메뉴들" :key="i">{{ a }}</a> -->
  </div>

  <div v-for="i in products" :key="i">
    <h4>{{ i.n }}</h4>
    <p>{{ i.p }}만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return  {
      products : [ {n :'역삼동원룸', p : 60},{n :'천호동원룸', p :70},{n :'마포구원룸', p: 80}],
      메뉴들 :  ['Home','Shop','About'],
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
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color : white;
  padding: 10px;
}
</style>
