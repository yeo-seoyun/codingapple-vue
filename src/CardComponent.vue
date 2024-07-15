<template lang="">
  <div>
    <img :src="원룸.image" alt="room0" class="room-img ">
    <h4 @click="$emit('openModal')" >{{ 원룸.title }}</h4>
    <!-- custom event
      부모가 가진 데이터를 바꾸고 싶으면 자식컴포넌트는 부모에게 메세지를 주어야한다.
      @click="$emit('작명') -> 부모 컴포넌트에게 전달하기
    -->
    <p>{{ 원룸.price }}원</p>
  </div>
</template>
<script>
// props 받아 온 데이터는 변경 불가
export default {
  name : 'CardComponent',
  props : {
    원룸 : Object,
  }
}
</script>
<style lang="">
  
</style>