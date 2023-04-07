<template>
  <div class="black-bg" v-if="모달창열렷니 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <img :src="원룸들[누른거].image" class="modal-img">
      <p>가격 : {{ 원룸들[누른거].price }}원</p>
      <TheDiscount/>
      <!-- <button @click="모달창열렷니=false">닫기</button> -->
    </div>
  </div>
</template>

<script>
import TheDiscount from './TheDiscount.vue';
export default {
    name : 'ModalView',
    props :{
      원룸들 : Array,
      누른거 : Number,
      모달창열렷니 : Boolean,
    },
    components: {
      TheDiscount : TheDiscount,
    }
}
</script>

<style>

</style>

