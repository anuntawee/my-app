<template>
  <section>
    <img src="./assets/logo.png" alt="">
    <h1>ชื่อ ผู้สมัครงาน : {{firstname}}</h1>
    <h1>{{lastname}}</h1>
    <h1>{{age}}</h1>
    <h1>{{800+200}}</h1>
    <p>ที่อยู่ <span v-html="address"></span></p>
    <h1></h1>
  </section>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App', 
  data(){
    return{
      firstname:"anuntawee",
      lastname:"onarun",
      age:20,
      address: "<i>ทดสอบ</i>"
    }
  }
  // components: {
  //   HelloWorld
  // }
}

</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
