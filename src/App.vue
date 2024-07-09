<template>

  <div class="menu">
    <a v-for="(상단메뉴,i) in 메뉴들" :key="i">{{ 상단메뉴 }}</a>
    <!-- <a v-for="상단메뉴 in 메뉴들" :key="상단메뉴">{{ 상단메뉴 }}</a> -->
  </div>

  <!-- Vue의 HTML 반복문 <태그 v-for="작명 in 횟수 :key="작명"> -->
  <!-- Vue 반복문 특징
    1. array/object 집어넣기 가능
    -> 자료안의 데이터 갯수만큼 반복
    -> 작명한 변수는 데이터안의 자료가 됨
    2. 변수 작명 2개까지 가능
    -> 왼쪽 변수는 array내의 데이터
    -> 오른쪽 변수는 1씩 증가하는 정수
    -->

  <div v-for="(상가,i) in products" :key="i">
    <h4>{{ 상가 }}</h4>
    <!-- <h4>{{ products[i] }}</h4> -->
    <p>60 만원</p>
  </div>

</template>

<!-- {{데이터바인딩}}을 하는 이유
  1. HTML에 하드코딩을 하면 추후 변경이 어려움
  2. Vue의 실시간 자동 렌더링 기능 사용 
  -> Vue는 data를 변경하면 data와 관련된 HTML도 실시간으로 변경 됨 
  = 웹앱 사이트 만들 수 있음
-->

<script>


export default {
  name: 'App',
  data(){
    return {
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
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
