<template>
  <div class="menu">
    <a v-for="i in 메뉴들" :key="i">{{ i }}</a>
  </div>

  <div v-if="1 == 2">
    안뇽
  </div>
  <div v-else-if=" 1 == 3">
    바보
  </div>
  <div v-else>
    몰랑
  </div>

  <div class="black-bg" v-if="모달창열렷니 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <img :src="원룸들[누른거].image" class="modal-img">
      <p>가격 : {{ 원룸들[누른거].price }}원</p>
      <button @click="모달창열렷니=false">닫기</button>
    </div>
  </div>

  <div v-for="(a, i) in 원룸들" :key="i">
    <img :src="a.image" class="room-img">
    <h4 @click="모달창열렷니 = true; 누른거 =i">{{ a.title }}</h4>
    <p>{{ a.price }}만원</p>
  </div>
</template>

<script>
import roomData from './assets/room';

export default {
  name: 'App',
  data(){
    return  {
      누른거 : 0,
      원룸들 : roomData,
      메뉴들 :  ['Home','Shop','About'],
      모달창열렷니 : false,
    }
  },
  components: {
  }
}
</script>

<style>
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 
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
.room-img {
  width: 100%;
  margin-top : 40px
}
.modal-img  {
  width: 100%;
}

</style>
