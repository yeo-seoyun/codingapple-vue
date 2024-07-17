<template lang="">
  <div class="black-bg" v-if="모달창열림 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[클릭].title }}</h4>
      <p>{{ 원룸들[클릭].content }}</p>
      <p>{{ 원룸들[클릭].price }}</p>
      <button @:click="$emit('closeModal')">닫기</button>
      <!-- props로 받아 온 건 read-only -->
    </div>
  </div>
</template>
<script>
  export default {
    name : 'ModalComponent',
    props : {
      원룸들 : Array,
      클릭 : Number,
      모달창열림 : Boolean,
    }
    // props:{ 데이터이름:자료형이름(형식) }
  }
</script>
<style lang="">
  
</style>