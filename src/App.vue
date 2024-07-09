<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4>xx 원룸</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>xx 원룸</h4>
    <p>{{ price2 }} 만원</p>
  </div>

</template>

<!-- {{데이터바인딩}}을 하는 이유
 1. HTML에 하드코딩을 하면 추후 변경이 어려움
-->

<script>


export default {
  name: 'App',
  data(){
    return {
      price1 : 60,
      price2 : 70,
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
