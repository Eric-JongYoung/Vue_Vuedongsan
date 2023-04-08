<template>
  <div class="menu">
    <a v-for="i in 메뉴들" :key="i">{{ i }}</a>
  </div>

  <TheDiscount v-if="showDiscount == true "/>

  <Transition name="fade">
    <ModalView @closeModal="모달창열렷니 = false" :원룸들="원룸들" :누른거="누른거" :모달창열렷니="모달창열렷니" />
  </Transition>

  <button @click="priceSort">가격순 정렬</button>
  <button @click="sortBack">되돌리기</button>
  
  <CardRoom @openModal="모달창열렷니 = true; 누른거 = $event" :원룸="원룸들[i]" v-for="(작명, i) in 원룸들" :key="작명"/>

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
      원룸들오리지널 : [...roomData], // 사본데이터로 저장
      showDiscount : true,
    }
  },
  methods :{
    priceSort(){
      this.원룸들.sort(function(a, b){
        return a.price - b.price
      })
    },
    sortBack(){
      this.원룸들 = [...this.원룸들오리지널];
    }
  },
  mounted(){
    //mount 되고나서 2초뒤에 닫아주삼
    //arrow funtion 으로 해야함
    setTimeout(()=>{
      this.showDiscount = false;
    },30000);
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

.fade-enter-from {
  /* 시작스타일 */
  transform: translateY(-1000px);
}
.fade-enter-active  {
  transition: all 1s;
}
.fade-enter-to  {
  /* 끝 스타일 */
  transform: translateY(0px);
}

.fade-leave-from {
  /* 시작스타일 */
  opacity: 1;
}
.fade-leave-active  {
  transition: all 1s;
}
.fade-leave-to  {
  /* 끝 스타일 */
  opacity: 0;
}
</style>
