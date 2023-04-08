<template>
  <div class="black-bg" v-if="모달창열렷니 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <img :src="원룸들[누른거].image" class="modal-img">
      <!-- <input @input="month = $event.target.value"> -->
      <input v-model="month">
      <select v-model="month">
        <option>3</option>
        <option>5</option>
      </select>
      <input v-model.number="month">
      <p> {{ month }} 개월 선택함 : {{ 원룸들[누른거].price * month }}원</p>
      
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>

export default {
    name : 'ModalView',
    data(){
      return{
        month : 1,  
      }
    },
    props :{
      원룸들 : Array,
      누른거 : Number,
      모달창열렷니 : Boolean,
    },
    components: {
      
    }
}
</script>

<style>

</style>

