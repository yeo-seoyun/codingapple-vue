<template>

  <div class="black-bg" v-if="모달창열림 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지내용</p>
      <button @:click="모달창열림 = false">닫기</button>
    </div>
  </div>
  <!-- 동적인 UI 만드는 법
    0. 화면 디자인 
    1. UI의 현재 상태를 데이터로 저장
    2. 데이터에 따라 UI가 어떻게 보일지 작성  

    v-if="조건식" -> 조건식이 true일 때만 HTML을 보여줌
  -->

  <div class="menu">
    <a v-for="(상단메뉴,i) in 메뉴들" :key="i">{{ 상단메뉴 }}</a>
  </div>


  <div>
    <img src="./assets/room0.jpg" alt="room0" class="room-img ">
    <h4 @:click="모달창열림 = true">{{ products[0] }}</h4>
    <p>60 만원</p>
      <!-- v-on:click="" -->
    <button @:click="신고수[0]++">허위매물신고</button> <span>신고수 : {{ 신고수[0] }}</span>
    <!-- 변수에 ++ (1씩 증가) -->
    <!-- Vue는 데이터가 변하면 HTML은 자동으로 변경됨 -->
  </div>
  <div>
    <img src="./assets/room1.jpg" alt="room1" class="room-img ">
    <h4>{{ products[1] }}</h4>
    <p>50 만원</p>
    <button @:click="신고수[1]++">허위매물신고</button> <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" alt="room2" class="room-img ">
    <h4>{{ products[2] }}</h4>
    <p>70 만원</p>
    <button @:click="신고수[2]++">허위매물신고</button> <span>신고수 : {{ 신고수[2] }}</span>
  </div>

</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      // 현재 UI가 어떻게 보일지 (현재상태)?
      모달창열림 : false, 
      신고수 : [0, 0, 0],
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  // Vue에서 함수 만드는 방법
  // Vue에서 함수 만들때 주의사항 -> 함수안에서 데이터를 불러올 때에는 this.데이터명
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
