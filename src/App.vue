<template>
  <div class="menu">
    <a v-for="i in 메뉴들" :key="i">{{ i }}</a>
  </div>

  <!-- <TheDiscount></TheDiscount> -->

  <TheDiscount v-bind="오브젝트" :이름="오브젝트.name" :나이="오브젝트.age" />


  <ModalView :원룸들="원룸들" :누른거="누른거" :모달창열렷니="모달창열렷니" />


  <CardRoom :원룸="원룸들[i]" v-for="(작명, i) in 원룸들" :key="작명"/>

  <!-- <div v-for="(a, i) in 원룸들" :key="i">
    <img :src="a.image" class="room-img">
    <h4 @click="모달창열렷니 = true; 누른거 =i">{{ a.title }}</h4>
    <p>{{ a.price }}만원</p>
  </div> -->
</template>

<script>
import roomData from './assets/room';
import TheDiscount from './components/TheDiscount.vue';
import ModalView from './components/ModalView.vue';
import CardRoom from './components/CardRoom.vue';

export default {
  name: 'App',
  data(){
    return  {
      누른거 : 0,
      원룸들 : roomData,
      메뉴들 :  ['Home','Shop','About'],
      모달창열렷니 : false,
      오브젝트 : { name : 'jong', age : 20 },
    }
  },
  components: {
    TheDiscount : TheDiscount,
    ModalView : ModalView,
    CardRoom : CardRoom,
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
