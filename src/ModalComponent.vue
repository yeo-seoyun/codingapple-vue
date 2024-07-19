<template lang="">
  <div class="black-bg" v-if="모달창열림 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[클릭].title }}</h4>
      <p>{{ 원룸들[클릭].content }}</p>
      <!-- <input @input="month = $event.target.value"> -->
      <!-- <input>에 입력한 값을 데이터로 저장할 때 "data = $event.target.value"로 사용-->
      <!-- 축약 방법 v-model -->
      <input v-model="month">
      <!-- <input v-model.number="month"> = 숫자로 저장 -->
      <p> {{ month }}개월 선택 : {{ 원룸들[클릭].price * month }}</p>
      <button @:click="$emit('closeModal')">닫기</button>
      <!-- props로 받아 온 건 read-only -->
    </div>
  </div>
</template>
<script>
  export default {
    name : 'ModalComponent',
    data() {
      return {
        month : 1,
        // 문자로 받을때는 초기값을 문자로 설정
      }
    },
    // watch : { 감시할데이터(){}} -> data 감시
    watch : {
      // month 데이터가 변할 때마다 watcher도 실행됨
      month(a) {
        if (a >= 13) {
          alert('13이상은 입력하지 마세요')
        }
      }
    },
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