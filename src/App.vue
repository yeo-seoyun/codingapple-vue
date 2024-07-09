<template>

  <div class="menu">
    <a v-for="(상단메뉴,i) in 메뉴들" :key="i">{{ 상단메뉴 }}</a>
  </div>

  <div>
    <h4>{{ products[0] }}</h4>
    <p>60 만원</p>
      <!-- v-on:click="" -->
    <button @:click="increase">허위매물신고</button> <span>신고수 : {{ 신고수 }}</span>
    <!-- 변수에 ++ (1씩 증가) -->
    <!-- Vue는 데이터가 변하면 HTML은 자동으로 변경됨 -->
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>70 만원</p>
  </div>

</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      신고수 : 0,
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  // Vue에서 함수 만드는 방법
  // Vue에서 함수 만들때 주의사항 -> 함수안에서 데이터를 불러올 때에는 this.데이터명
  methods : {
    increase(){
      this.신고수 += 1;
    },
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
