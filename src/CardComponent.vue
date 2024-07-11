<template lang="">
  <div>
    <img :src="원룸.image" alt="room0" class="room-img ">
    <h4 @:click="모달창열림 = true; 클릭 = i">{{ 원룸.title }}</h4>
    <p>{{ 원룸.price }}원</p>
  </div>
</template>
<script>
export default {
  name : 'CardComponent',
  props : {
    원룸 : Object,
  }
}
</script>
<style lang="">
  
</style>