<template>

  <div class="black-bg" v-if="모달창열림 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지내용</p>
      <button @:click="모달창열림 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(상단메뉴,i) in 메뉴들" :key="i">{{ 상단메뉴 }}</a>
  </div>


  <div v-for="(room, i) in 원룸들" :key="i">
    <img :src="room.image" alt="room0" class="room-img ">
    <!-- HTML 태그안의 속성 데이터바인딩은 :으로 시작 -->
    <h4 @:click="모달창열림 = true">{{ room.title }}</h4>
    <p>{{ room.price }}원</p>
  </div>

</template>

<script>

import rooms from './assets/rooms.js'

export default {
  name: 'App',
  data(){
    return {
      모달창열림 : false, 
      신고수 : [0, 0, 0],
      메뉴들 : ['Home', 'Shop', 'About'],
      // products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      원룸들 : rooms,
    }
  },
  methods : {
    // increase(){
    //   this.신고수[0] += 1;
    // },
  },
  components: {

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
