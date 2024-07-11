<template>

  <!-- 
  <div v-if="1 == 2">
    <p>안녕하세요</p>
  </div>
  <div v-else>
    <p>안녕하세요2</p>
  </div> 
  <div v-else-if="1 == 3">
    <p>안녕하세요2</p>
  </div> 
  -->

  <!-- props로 데이터 전송하여 사용하기
    <자식 v-bind:데이터="데이터">

    데이터를 만들때에는 최상위 컴포넌트에 작성하는 것이 좋음
  -->
  <Modal :원룸들="원룸들" :클릭="클릭" :모달창열림="모달창열림" />

  <div class="menu">
    <a v-for="(상단메뉴,i) in 메뉴들" :key="i">{{ 상단메뉴 }}</a>
  </div>


  <!-- 컴포넌트로 분리하기 -->
  <Discount />

  <div v-for="(room, i) in 원룸들" :key="i">
    <img :src="room.image" alt="room0" class="room-img ">
    <h4 @:click="모달창열림 = true; 클릭 = i">{{ room.title }}</h4>
    <p>{{ room.price }}원</p>
  </div>

</template>

<script>

import rooms from './assets/rooms.js'
import DiscountComponent from './DiscountComponent.vue';
import ModalComponent from './ModalComponent.vue';

export default {
  name: 'App',
  data(){
    return {
      모달창열림 : false, 
      신고수 : [0, 0, 0],
      메뉴들 : ['Home', 'Shop', 'About'],
      // products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      원룸들 : rooms,
      클릭 : 0,
    }
  },
  methods : {
    // increase(){
    //   this.신고수[0] += 1;
    // },
  },
  components: {
    Discount : DiscountComponent,
    Modal : ModalComponent,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

/* 모달창 */
.black-bg {
  width: 100%;
  height: 100%;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
