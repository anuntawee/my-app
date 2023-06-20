<template>
  <section>
    <img v-bind:src="picture" v-bind:width="size" v-bind:height="size">
    <img :src="picture" :width="size" :height="size">
    <img src="./assets/logo.png" alt=""> <br>
    ป้อนชื่อเล่น <input type="text" v-on:input="setnickname"/>
    <form @submit.prevent="submitform">
      <label for="">ป้อนชื่อเล่น</label>
      <input type="text" v-on:input="setnickname">
      <button type="submit">submit</button>
    </form>
    <h1>ชื่อ-นามสกุล ผู้สมัครงาน : {{firstname}} {{lastname}}</h1>
     <h1>ชื่อ-นามสกุล ผู้สมัครงาน : {{getFullname()}}</h1>
    <h1>ชื่อเล่น : {{nickname}}</h1>
     <h1>{{age}}</h1>
  
    <p>ที่อยู่ <span v-html="address"></span></p>
    <a :href="social">facebook</a>
    <p>งานอดิเรก</p> <!-- เรียกใช้งาน array -->
    <!-- <ul>
      <li>{{hobby[0]}}</li>
      <li>{{hobby[1]}}</li>
      <li>{{hobby[2]}}</li>
      <li>{{hobby[3]}}</li>
    </ul>
    <p>ข้อมูลพื้นฐาน</p>
    <ul>
      <li> เพศ {{general.gender}}</li>
      <li> น้ำหนัก {{general.weight}}</li>
      <li> ส่วนสูง {{general.height}}</li>
      <li> โรคประจำตัว {{general.status}}</li>
    </ul> -->

    <button v-on:click="showdata">คลิกเพื่อดูข้อมูล</button>
    <button @click="showdata">คลิกเพื่อดูข้อมูล</button> <!--เขียนได้ สองแบบ-->
    <button  @click="increment">เพิ่ม</button>
    <button  @click.left="incrementt(10)">เพิ่ม</button>  <!--คลิกได้เฉพาะด้านขวา-->
    <button @click.ctrl="decrement">ลด</button> <!--คลิกได้เฉพาะกดปุุ่ม ctrl-->
    <button @click.right="decrementt(5)">ลด</button>  <!--คลิกได้เฉพาะด้านซ้าย-->


    


  </section>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App', 
  data(){ //ข้อมูลต้องสร้างใน คำสั่ง data
    return{
      firstname:"anuntawee",
      lastname:"onarun",
      nickname:"",
      age:20,
      address: "<i>ทดสอบ</i>",
      picture:"https://cdn-icons-png.flaticon.com/512/4308/4308230.png",
      size:150,
      social:"https://www.facebook.com",
      hobby:["เล่นเกม","ฟังเพลง","นอน","เที่ยว"], //เก็บค่าแบบ aray
      general:{gender:"ชาย",weight:60,height:170,status:false} //เก็บข้อมูล sting boolena ตัวเลข
    }
  },
  methods:{ //function ต้องสร้างใน metdos
    getFullname(){
         return this.firstname + this.lastname
    },
    showdata(){
      alert(this.firstname)
    },
    increment(){
      this.age++
    },
    incrementt(val){
      this.age+=val
    },
    decrement(){
      this.age--
    },
    decrementt(val){
      this.age-=val
    },
    setnickname(event){
        console.log(event.target.value);
        this.nickname=event.target.value
    },
    submitform(e){
      e.preventDefault();
      alert("บันทึกเรียบร้อย")
    }
  }
  // components: {
  //   HelloWorld
  // }
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
