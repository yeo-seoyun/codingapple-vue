<template lang="">
  <div>
    <img :src="원룸.image" alt="room0" class="room-img ">
    <h4 @click="$emit('openModal', 원룸.id)" >{{ 원룸.title }}</h4>
    <!-- custom event
      부모가 가진 데이터를 바꾸고 싶으면 자식컴포넌트는 부모에게 메세지를 주어야한다.
      @click="$emit('작명', 데이터) -> 부모 컴포넌트에게 전달하기
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
  },
  // 함수로 만들어서 사용할때는 this를 붙여준다. 함수명은 영어로!
  // methods : {
  //   함수(){
  //     this.$emit('openModal', this.원룸.id)
  //   }
  // }
}
</script>
<style lang="">
  
</style>