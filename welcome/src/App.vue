<template>


  <div>



    <div class="black-bg" v-if="isModalOpen == true">
      <div class="white-bg">

        <h4>상세페이지입니다.</h4>
        <p>새는 왱알옹알</p>
        <button @click="isModalOpen = false">창 닫기</button>

      </div>


    </div>



    <menu class="menu">
    <a v-for="(i,a) in menus" :key="i">{{ a+1 }}. {{ i }}</a> 
    <!-- v-for=" A in B ". B가 배열이면 A는 배열값으로도 기능함. a는 0부터 시작하는 정수임.-->
    </menu>

    <!-- <article>
      <button @click="increase" @mouseover="mouse++">허위매물신고</button>
      <h4>신고 수 : {{ report }}</h4>
      <p>마우스 오버 : {{ mouse }} <br><br> </p> 
    </article> -->
    

    <main>
    

      <article v-for="(b, j) in products" :key="j">
      
       
       <h4 @click="isModalOpen = true">{{ b }}</h4>
       <p>{{ price[j] }}</p>
       <button @click="increase(j)">허위매물신고</button>
        <p>신고 수 : {{ report[j] }}</p>
       </article>



    </main>
  <img alt="welcome" src="./assets/neuro_asdf-removebg-preview.png">
  
  
  
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      isModalOpen : false,
      report : [0, 0, 0],
      mouse : 0,
      price : [60, 70, 100],

      products : ['강화읍', '춘천시', '양구군'],
      menus : ['Home', 'Products', 'About', 'Shop'],
    }
  },
  methods: {
    increase(i) {
      this.report[i]++;
    }
  },

  components: {
    
  }
}
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkgray;
  padding: 15px;
}

.menu a {
  color :aliceblue;
  padding: 10px;
}


</style>
