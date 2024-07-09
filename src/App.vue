<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <!-- {{ logo }} -->
    <h4 class="red" :style="스타일">xx 원룸</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>xx 원룸</h4>
    <p>{{ price2 }} 만원</p>
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
      price1 : 60,
      price2 : 70,
      // logo : '원룸샵', -> 자주 변경되지 않는 데이터는 바인딩 하지 않음
      스타일 : 'color : blue',
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
  margin-top: 60px;
}
</style>
